---
title: "搭建个人工作台部署一些工具的每周操作记录Week of August 17th"
date: 2026-08-23T00:00:00+08:00
draft: false
---
电脑配置：
台式机：GMK-EXO2 AIMAX365, 128GB 2T
智能体：Opencode
云模型：Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3.8 27b, Qwen3.6-35B-A3B，sensevoice onnx, fast-whispter,whisper系列模型

笔记本电脑：联想thinkpad T14p 32GB,  图形卡128MB，存储1T
智能体：Opencode
云模型：Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3:8b 

---
8月13日Deepseek Harness发布之后，我第一时间下载并且尝试了一些操作。
目前体验：
1. 如果用其他模型，消耗token特别快。Deepseek v4 Pro/Flash的适配度更好，但是消耗也很大。
2. 因为是web UI, 重启都要在对应的命令端里操作，对新手特别不友好。我反复操练了4到5次才记住相关的操作。
3. Trajectory轨迹这一块能显示智能体tool call之类的过程，结合Li Bojie的AI-Agents-in-Depth（github有项目) 一书来学习，能让普通人比较深度得了解智能体的工作模式，合适不满足于B站油管视频科普的普通人。（这点是DSH和其他智能体非常不同的地方，符合审计需要的audit trail要求）

![DSH 截图](/images/20260823_DSH.png)

其余几天尝试了用Tailscale连接云模型电脑和本地部署电脑。现在能达到用笔记本电脑发送指令调用迷你主机里的Opencode进行一些操作，比如指挥迷你主机里面的opencode跑本地模型。踩坑的地方有MiniMax一开始给我的JSON代码在最后一个括号后面会有逗号，代码未生效，笔记本电脑死活连不上迷你主机；最后换了模型DeepSeek，帮我检查出来这段代码有错误。

另外，目前AMD lemonade还是在Windows里面操作比较好，WSL里面操作，再去做一些其它安装的时候，会碰到软件不适配的障碍。这坑踩了两天，让人心情沮丧。

<本博客更新频率预计本周一篇>
<同名博客kslizhong.cn; my-profile-website.pages.dev>


