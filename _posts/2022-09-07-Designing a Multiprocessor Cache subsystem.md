---
title: 'Designing a Multiprocessor Cache subsystem'
date: 2024-04-08
permalink: /posts/2024/04/blog-post-1/
tags:
  - cool posts
  - category1
  - category2
---

This is a sample blog post. Lorem ipsum I can't remember the rest of lorem ipsum and don't have an internet connection right now. Testing testing testing this blog post. Blog posts are cool.

Headings are cool
======

You can have many headings
======

Aren't headings cool?
------

6 Arm Memory Instruction Set
	指令集分类
		整型load/store
		浮点和SIMD load/store
		Exclusive load/store
		Cache维护指令
		DCache Zero指令
		TLB维护指令
		软件预取指令
		地址翻译AT指令
		Barrier指令
		功耗管理指令wfi/wfe
	6.1 Elements
		load/store都以elements为单位进行操作，可以是单个字节、半字、字、双字、四字
		exclusive的操作是按照完整的访问大小进行检查
		Alignment Flag如果设置，则非对齐的访问会报错
		非对齐的访问会导致额外的latency
	7.15 Forward progress guarantees for WLU/WU
		snoop相比WU/WLU优先级高，否则会导致死锁：SI buffer全满且头部就是WLU，发出snoop后如果被其他cluster的WU挡住，那么该WU会因为SI buffer全满而无法继续处理，形成死锁
	7.16 Cache Maintenance
		address based
		set/way
