---
layout: post
title: RingBuffer-环形缓冲区
date: 2017-09-18 18:07:00.000000000 +9:00
tag: Util
---

>
> RingBuffer
>

```C++
class RingBuffer
{
public:
	RingBuffer(int size);
	virtual ~RingBuffer();

	inline int GetCapacity() { return capacity; }

	int ReadCount();
	int WriteCount();

	int Read(void* data, int count);
	int Write(const void* data, int count);

private:
	RingBuffer();
	RingBuffer(const RingBuffer&);

private:
	int capacity;
	char* buffer;

	// 读区域
	char* head;
	// 写区域
	char* tail;
};
```

**head指向了读区域，tail指向了写区域！**

三种情况：
 * 1 head与tail都指向同一个地方时，可读区域大小为0
 * 1. 这种情况只会在缓冲区还使用时出现，开始使用之后，不会出现head/tail重合的现象，即tail永远不会等于head，否则head指向的数据还未读走就被覆盖了！
 
 * 2 head < tail  ，说明tail没有写到缓冲区末尾，从缓冲区开头重新开始。可读的区域自然为(tail - head)
 
 * 3 head > tail  ，说明tail已经从缓冲区末尾写完，并从开头处重新准备写了。

![图1](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/ring_buffer_01.png)

代码:
```C++
int ReadCount()
{
	if (head == tail)
		return 0;

	if(head < tail)
		return tail - head;

	return GetCapacity() - (head - tail);
}

int WriteCount()
{
	return GetCapacity() - ReadCount();
}
```

>
> 读数据 
>
> 从head指向的地址开始，读到data指向的地址处，读count个数据。返回读的个数
>

三种情况：
* 1 head < tail  ，此时要从count和"可读区域大小"中选一个较小的值，作为读操作的次数。避免了count 大于“可读区域”的错误。

* 2 head > tail  且 count 的个数**小于**“从head到缓冲区末尾的数据个数”图中蓝色。直接复制内存，再修改head指针即可。

* 3 head > tail  且 count 的个数**大于**“从head到缓冲区末尾的数据个数”。此时，先把从head到缓冲区末尾的值蓝色复制到data处，再把剩余的绿色复制过去。注意两个值：copy_sz 和*(data + copy_sz)

![图2](https://raw.githubusercontent.com/kevinfblog/kevinfblog.github.io/master/assets/blog-add/ring_buffer_02.png)

这种情况下，问题来了，要是绿色的区域超过了tail 怎么办？:）

所以，应该加了一个判断，这个在写操作中做了，但这里没做。即要读的个数count要小于可读区域的大小。

不然会出现head > tail 但head 指向的数据以及head后边的数据又不是有效数据，这个问题。

代码:
```C++
int Read(void* data, int count)
{
	if (head < tail)
	{
		int copy_sz = min(count, ReadCount());
		::memcpy(data, head, copy_sz);
		head += copy_sz;
		return copy_sz;
	}
	else
	{
		if (count < GetCapacity() - (head - buffer))
		{
			int copy_sz = count;
			::memcpy(data, head, copy_sz);
			head += copy_sz;
			return copy_sz;
		}
		else
		{
			int copy_sz = GetCapacity() - (head - buffer);
			::memcpy(data, head, copy_sz);
			head = buffer;
			copy_sz += Read(static_cast<char*>(data) + copy_sz, count - copy_sz);
			return copy_sz;
		}
	}

```

>
> 写数据
>
> 把数据从data指向的地址，写到tail 指向的地址，写count个。返回写的个数。
>
> 这里进来直接判断，要写入的内容大小要小于可写区域大小，防止造成数据覆盖。写入合法。
>

三种情况：

1、2 需要计算tail_avail_sz，这个值为tail 到缓冲区末尾的数据区域大小。

* 1 head < tail  ，count < tail_avail_sz 。直接复制内容。假如tail到了缓冲区末尾，让tail 回到缓冲区首地址。

* 2 head < tail  ，count > tail_avail_sz  。先写入 tail_avail_sz 个数据，tail 回到缓冲区首地址，再写入剩余的部分。

* 3 head > tail  ，这种情况最简单，由于已经做了写入合法判断，所以直接复制内容，修改tail 即可。


代码:
```C++
int Write(const void* data, int count)
{
	if (count >= WriteCount())
		return -1;

	if (head <= tail)
	{
		int tail_avail_sz = GetCapacity() - (tail - buffer);
		if (count <= tail_avail_sz)
		{
			::memcpy(tail, data, count);
			tail += count;
			if (tail == buffer + GetCapacity())
				tail = buffer;

			return count;
		}
		else
		{
			::memcpy(tail, data, tail_avail_sz);
			tail = buffer;

			return tail_avail_sz + Write((char*)data + tail_avail_sz, count - tail_avail_sz);
		}
	}
	else
	{
		::memcpy(tail, data, count);
		tail += count;
		return count;
	}
}
```
