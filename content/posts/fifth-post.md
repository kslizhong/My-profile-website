---
title: "搭建个人工作台部署一些工具的每周操作记录Week of August 31st"
date: 2026-09-08T00:00:00+08:00
draft: false
tags: ["周记", "智能体", "数学复习"]
description: "搭建个人工作台部署一些工具的每周操作记录Week of August 31st"

---
电脑配置：
台式机：GMK-EXO2 AIMAX365, 128GB 2T
智能体：Opencode
云模型：Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3.8 27b, Qwen3.6-35B-A3B，sensevoice onnx, fast-whispter,whisper系列模型

笔记本电脑：联想thinkpad T14p 32GB,  图形卡128MB，存储1T
智能体：Opencode
云模型：GLM-5.3-flash/Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3:8b 

---
本周根据AMD官方开发者战术手册（ [通过柠檬水服务器本地运行Hermes Agent |AMD AI Playbooks](https://developer.amd.com/playbooks/hermes-lemonade-server/)) ，在GMK主机上安装了Hermes agent。设计理念是用它来配合Opencode和云模型做一些简单重复操作和数据爬虫任务。我把hermes安装在了WSL2下，用Ubuntu终端来管理，hermes agent在podman沙盒中运行，产出物落在D盘。本地模型采用Qwen3.6-35B-A3B，由Lemonade server(llm.cpp)来管理。全程操作由opencode+GLM-5.3-flash来告诉我操作路径，我操作不了的地方请它自己操作。具体方法是：先切换plan模式，让opencode读取官方给的技术操作页面，然后对话两到三轮，确定技术实现路径。OK之后用build模式全程由opencode来落实安装hermes agent, 我来授权一些操作。

和周围的朋友聊智能体和大语言模型时我注意到很多人分不清楚两者之间的区别，鉴于互联网上一堆垃圾自媒体博文误导人心，我在这里推荐初学者理解agent智能体的学习网站有：
https://hello-agents.datawhale.cc/

<本博客更新频率预计本周一篇>
<同名博客kslizhong.cn; my-profile-website.pages.dev>


