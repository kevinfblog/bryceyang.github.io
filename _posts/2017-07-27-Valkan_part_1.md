---
layout: post
title: Vulkan Part 1
date: 2017-07-27 11:30:00.000000000 +9:00
tag: Vulkan
---

- 创建实例(VkInstance)
- 创建逻辑设备(VkPhysicalDevices)
- 设备属性(VkPhysicalDeviceProperties)和设备特性(vkGetPhysicalDeviceFeatures)
- 队列,队列家族
- 命令缓冲区



> 
> 一个 ***VkInstance*** 可以有多个 ***VkPhysicalDevices***
>
> 一个 ***VkPhysicalDevices*** 可以有多个 ***VkDevices***
> 

## 创建实例(vkCreateInstance)

调用 **vkCreateInstance()** 完成实例的创建

```创建实例
VkApplicationInfo application_info = {
    VK_STRUCTURE_TYPE_APPLICATION_INFO,     // VkStructureType          sType
    nullptr,                                // const void*              pNext
    "application name",                     // const char*              pApplicationName
    VK_MAKE_VERSION(1, 0, 0),               // uint32_t                 applicationVersion
    "engine name",                          // const char*              pEngineName
    VK_MAKE_VERSION(1, 0, 0),               // uint32_t                 engineVersion
    VK_API_VERSION                          // uint32_t                 APIVersion
};

VkInstanceCreateInfo instance_info = {
    VK_STRUCTURE_TYPE_INSTANCE_CREATE_INFO, // VkStructureType          sType
    nullptr,                                // const void*              pNext
    0,                                      // VkInstanceCreateFlags    flags
    &application_info,                      // const VkApplicationInfo* pApplicationInfo
    0,                                      // uint32_t                 enabledLayerCount
    nullptr,                                // const char**             ppEnabledLayer
    0,                                      // uint32_t                 enabledExtensionCount
    nullptr                                 // const char**             ppEnabledExtensionNames
};

if(vkCreateInstance(&instance_info, nullptr, &Vulkan.Instance) != VK_SUCCESS)
{
    std::cout << "cannot create Valkan instance!" << std::endl;
    return false;
}

return true;
```

#### VkApplicationInfo 参数意义:
* sType – 结构类型。 此处为 VK_STRUCTURE_TYPE_APPLICATION_INFO，即有关应用的信息。
* pNext – 留作将来使用。
* pApplicationName – 应用名称。
* applicationVersion – 应用版本，使用 Vulkan 宏创建版本非常方便。 它包括主要版本和次要版本，并将数字合成一个 32 位的值。
* pEngineName – 应用使用的引擎名称。
* engineVersion – 我们在应用中使用的引擎版本。
* apiVersion – 我们希望使用的 Vulkan API 版本。 最好提供包含时在 Vulkan 标头中定义的版本，这就是我们为什么使用在 vulkan.h 标头文件中查找的 VK_API_VERSION。

#### VkInstanceCreateInfo 参数意义:
* sTypes – 数据结构。在这种情况下，它通过提供 VK_STRUCTURE_TYPE_APPLICATION_INFO 的值，通知驱动程序我们将提供有关实例创建的信息。
* pNexts – 未来版本的 Vulkan API 可能会提供有关实例创建的其他信息，该参数用于此目的。 目前它留作将来使用。
* flags – 另一个留作将来使用的参数；目前必须设为 0。
* pApplicationInfo – 包含应用信息（比如名称、版本、所需 Vulkan API 版本等）的另一结构的地址。
* enabledLayerCount – 定义我们希望启用的实例级验证层的数量。
* ppEnabledLayerNames – 包含我们希望启用的层级名称的 enabledLayerCount 要素阵列。
* enabledExtensionCount – 我们希望启用的实例级扩展功能数量。
* ppEnabledExtensionNames – 与层级一样，该参数必须指向至少包含我们希望使用的实例级扩展功能的名称的enabledExtensionCount 要素的阵列。

定义完成上面两个结构体之后就可以调用 **vkCreateInstance()** 创建设备, 并且判断是否创建成功. 


## 创建逻辑设备()

创建之前,先要检查看系统中有多少可供因供应能够的物理设备.

获取所有可用的物理设备的句柄

```
uint32_t device_count = 0;
if( (vkEnumeratePhysicalDevices(Vulkan.Instance, &device_count, nullptr) != VK_SUCCESS ||
device_count == 0 )
{
    std::cout << "Error: occurred during physical devices enumeration!" << std::endl;
    return false;
}

std::vector<VkPhysicalDevice> physical_devices(device_count);
if(vkEnueratePhyusicalDevices(Vulkan.Instance, &device_count, & physical_devices[0])
 != VK_SUCCESS)
{
    std::cout << "Error: occurred during physical devices enumeration!" << std::endl;
    return false;
}

return true;
```

调用 **vkEnumeratePhysicalDevices()** 函数可以检查有多少设备.

注意看上面代码可见该函数调用了两次.

第一次最后一个参数传递的是nullptr.这样驱动程序会知道我们仅要求知道可用 的物理设备的数量.该数量保存在第二个参数 device_count 中.

第一次调用之后我们已经知道了可用物理设备的数量.接下来我们准备保存他们的句柄.就是接下来的第二次调用.

第二次调用 **vkEnumeratePhysicalDevices()** 所有参数都不等于nullptr.传递最后一个参数,驱动程序将句柄保存到该参数中.

> 值得注意的是:
> 
> 两次调用的返回值可能不同.

例如:

有4台可用物理设备，但我们只对第1台感兴趣。

因此在第一次调用后，在 device_count 中设置一个为 4 的值。

这样我们将知道这里有任意兼容 Vulkan 的设备，然后继续。

我们将该值覆写成 1，因为无论有多少设备，我们只希望使用 1 台设备。第二次调用后，我们将仅获取一个物理设备句柄。


现在我们已经有了所有兼容VK的物理设备的句柄,现在我们检查各设备的属性,如下

```
VkPhysicalDevice physical_device = VK_NULL_HANDLE;
uint32_t queue_family_index = UINT32_MAX;
for(uint32_t i = 0; i < device_count; ++i)
{
    if(CheckPhysicalDeviceProperties(physical_devices[i], queue_family_index)) // CheckPhysicalDeviceProperties 会在下文中讲到
    {
        physical_device = physical_devices[i];
    }
}
```
## 设备属性和设备特性

这部分分开说,先说设备属性

### 设备属性

**CheckPhysicalDeviceProperties()** 函数用来检查设备的属性.

如果检查通过,返回true,同时将队列家族索引保存在第二个参数中.

```CheckPhysicalDeviceProperties

bool CheckPhysicalDeviceProperties(VkPhysicalDevice physical_device, uint32_t& queue_family_index)
{
    VkPhysicalDeviceProperties device_properties;
    VkPhysicalDeviceFeatures device_features;

    vkGetPhysicalDeviceProperties(physical_device, &device_properties);
    vkGetPhysicalDeviceFeatures(physical_device, &device_features);

    uint32_t major_version = VK_VERSION_MAJOR(device_properties.apiVersion);
    uint32_t minor_version = VK_VERSION_MINOR(device_properties.apiVersion);
    uint32_t patch_version = VK_VERSION_PATCH(device_properties.apiVersion);

    if(
        (major_version < 1) &&
        (device_properties.limits.maxImageDimension2D < 4096)
    )
    {
        std::cout << "Physical device " 
        << physical_device << " doesn't support required parameters!"
        << std::endl;
        
        return false;
    }
    
    ...
}

```

这只是该函数的前半部分.检查了设备属性
* 支持的Vulkan API的版本
* 设备名称和类型(集成/独立GPU)
* 厂商ID和限制
* 限制描述如何创建大纹理,anti-aliasing中支持多少实例活着特定着色器阶段可以使用多少缓冲区

接下来是设备特性

### 设备特性

所谓特性就是拓展功能.驱动程序不是必须支持.默认情况下也不启用.
> ***Vulkan中默认不启用, 但Vulkan规范支持,部分特性可能会对性能和稳定性造成影响***

## 队列,队列家族

在OpenGL中这部分是是有驱动程序完成的,而Vulkan中直接暴漏给了用户.

事实上在OpenGL中我们调用GL的函数并非直接把每个请求单独直接下发到通信总线,这样相率很低.

最好的做法是收集起来 分组传递.

而这些队列都要通过 **命令缓冲区** 传递到硬件.

这些缓冲区抱恨不同的操作类型.比如图形命令或者计算命令.特定的命令可能由特定的硬件处理,因此队列也可分成不同的类型.

在Vulkan中,这些对垒类型是调用的家族.每个队列家族都可支持不同的操作类型.因此我们还必须检查特定物理设备是否支持我们希望执行的操作类型.

另外,我们还可以在一台设备商执行一类操作,在令一台设备上执行令一类操作,但需要检查他的可行性.这类检查由 **CheckPhysicalDeviceProperties()的后半部分完成**

```CheckPhysicalDeviceProperties

bool CheckPhysicalDeviceProperties(VkPhysicalDevice physical_device, uint32_t& queue_family_index)
{
    ...
    uint32_t ququq_families_count = 0;
    vkGetPhysicalDeviceQueueFamilyProperties(physical_device, & queue_famliles_count, nullptr);
    if(queue_families_count == 0)
    {
        std:: cout << "Physical device "
        << physical_device
        << "doesn't have any queue families!"
        << std::endl;
        
        return false;
    }
    
    std::vector<VkQueueFamilyProperties> queue_family_properties(queue_families_count);
    vkGetPhysicalDeviceQueueFamilyProperties(physical_device, &queue_families_count, &queue_family_properties[0]);
    for(uint32_t i = 0; i < queue_families_count; ++i)
    {
        if((queue_family_properties[i].queueCount > 0) && 
        (queue_family_properties[i].queueFlags & VK_QUEUE_GRAPHICS_BIT))
        {
            queue_family_index = i;
            return true;
        }
    }
    
    std::cout << "cannot find queue family with required properties on physical device" << std::endl;
    
    return false;
}
```

上半部分检查物理设备中有多少可用的队列家族,其检查方式和枚举物理设备的方法类似.

首先调用 **vkGetPhysicalDeviceQueueFamilyProperties()**,其中最后一个参数是nullptr,这样在 queue_famliles_count 中保存不同队列家族的可变数量.

接下来为该数量的对接家族的属性准备一个位置

然后在次调用 **vkGetPhysicalDeviceQueueFamilyProperties()** 函数,保存个队列家族的属性到queue_family_properties中.

各队列家族的属性包含
* 对接标记
* 家族中可用对接的属性
* 时间戳
* 图像传输粒度

重要部分是:家族中的队列数量和标记

标记定义特定对接家族支持的操作类型(位运算 可以支持多种)

操作类型(VkQueueFlagBits)
* 图形 VK_QUEUE_GRAPHICS_BIT
* 计算 VK_QUEUE_COMPUTE_BIT
* 传输 VK_QUEUE_TRANSFER_BIT
* 稀疏绑定 VK_QUEUE_SPARSE_BINDING_BIT
* 未来可能出现的其他操作

```VkQueueFlagBits
typedef enum VkQueueFlagBits {
    VK_QUEUE_GRAPHICS_BIT = 0x00000001,
    VK_QUEUE_COMPUTE_BIT = 0x00000002,
    VK_QUEUE_TRANSFER_BIT = 0x00000004,
    VK_QUEUE_SPARSE_BINDING_BIT = 0x00000008,
} VkQueueFlagBits;
```

以 检查图形操作 为例子, 如果找到该支持,那么就可以使用特定物理设备.

我们还需牢记指定的家族索引

选择物理设备后,我们可以创建将在应用其他部分代表该设备的逻辑设备

```
if(physical_device == KV_NULL_HANDLE)
{
    std::cout << "cannot select physical device based on the chosed properties!" << std::endl;
}

std::vector<float> queue_priorities = {1.0f};

VkDeviceQueueCreateInfo queue_create_info = {
    VK_STRUCTURE_TYPE_DEVICE_QUEUE_CREATE_INFO,
    nullptr,
    0,
    queue_family_index,
    static_cast<uint32_t>(queue_priorities.size()),
    &queue_priorities[0]
};

VkDeviceCreateInfo device_create_info = {
    VK_STRUCTURE_TYPE_DEVICE_CREATE_INFO,
    nullptr,
    0,
    1,
    &queue_create_info,
    0,
    nullptr,
    0,
    nullptr,
    nullptr
};

if(vkCreateDevice(physical_device, &device_create_info, nullptr, &Vulkan.Device) != VK_SUCCESS)
{
    std::cout << "cannot create Vulkan device!" << std::endl;
    return false;
}

Vulkan.QueueFamilyIndex = queue_family_index;
return true;
```

 **VkDeviceCreateInfo** 内容如下:
 * sType – 所提供结构的标准类型，此处的 VK_STRUCTURE_TYPE_DEVICE_CREATE_INFO 表示我们为设备创建提供参数
 * pNext – 指向扩展特定结构的参数；此外我们设为 nullptr。
 * flags – 另一留作将来使用的参数，必须是 0。
 * queueCreateInfoCount – 不同队列家族的数量，我们通过它创建队列和设备。
 * pQueueCreateInfos – queueCreateInfoCount 要素（指定我们希望创建的队列）阵列的指示器。
 * enabledLayerCount – 待启用的设备级验证层数量。
 * ppEnabledLayerNames – 包含待启用设备级的 enabledLayerCount 名称的阵列的指示器。
 * enabledExtensionCount – 为设备启用的扩展功能数量。
 * ppEnabledExtensionNames – 包含 enabledExtensionCount 要素的指示器；各要素必须包含应该启用的扩展功能的名称。
 * pEnabledFeatures – 结构指示器（表示为该设备启用的其他特性）（请参阅“设备”部分）。
 

 **VkDeviceQueueCreateInfo** 内容如下
 * sType – 结构类型，此处 VK_STRUCTURE_TYPE_DEVICE_QUEUE_CREATE_INFO 表示它为队列创建信息。
 * pNext – 为扩展功能预留的指示器。
 * flags – 留作将来使用的值。
 * queueFamilyIndex – 队列家族（通过它创建队列）的索引。
 * queueCount – 我们希望在特定队列家族中启用的队列数量（希望通过该家族使用的队列数量）以及pQueuePriorities 阵列中的要素数量。
 * pQueuePriorities – 包含浮点值（描述通过该家族在各队列中执行的操作的优先级）的阵列。

## 命令缓冲区

