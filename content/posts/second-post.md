---
title: "搭建个人工作台部署一些工具的每周操作记录Week of August 10th"
date: 2026-08-13T00:00:00+08:00
draft: false
tags: ["语音转文字", "本地部署","端侧AI"]
description: "搭建个人工作台部署一些工具的每周操作记录Week of August 10th"

---

电脑配置：
台式机：GMK-EXO2 AIMAX365, 128GB 2T
智能体：Opencode
云模型：Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3.6-35B-A3B，sensevoice onnx, fast-whispter,whisper系列模型

笔记本电脑：联想thinkpad T14p 32GB,  图形卡128MB，存储1T
智能体：Opencode
云模型：Deepseek-V4-Flash/MiniMax M3
本地模型：Qwen3:8b

## Obsidian 同步
家庭局域网内通过开源软件Syncthing将Obsidian的笔记文档同步
思考：这个操作适用于同一个局域网中的任何设备文档同步。限制是同步的设备必须同时处于运行状态。

## 语音转文字
台式机+本地模型
最终部署结果：sensevoice onnx (source: modelscope)

第一步：sensevoice_chunk.py将音频分段转写
SenseVoice + onnxruntime 分块转写（GPU/DML 稳定版）
- 将长音频切成 CHUNK_SEC 秒的块，逐块推理（避免超大张量导致 DML 崩溃）
- 输出带时间戳的分段文本

第二步：batch_audio_to_text.py将批量音频转成文字，转英文时注意用空格作为单词之间的分隔
批量音频转文字工具（Windows 原生 + AMD GPU / DirectML）
- 支持任意音频格式（m4a/mp3/flac/wav/aac/ogg...），自动用 ffmpeg 转 16kHz mono wav
- 用 onnxruntime-directml 在 AMD GPU 上跑 SenseVoice 转写
- 批量处理：传入一个文件夹，或直接拖多个文件进来
- 输出：每个音频同目录生成同名 .txt（带时间戳分段）

扩展：台式机另外还本地部署了B站视频的语音自动转成文字稿的命令行工具集成。基于 `lanbinleo/bili2text`，自定义了模型路径、引擎（faster-whisper + SenseVoice）和若干补丁。

笔记本电脑由于内存限制，没有部署。

## 翻译软件
台式机+本地模型
最终部署结果：Qwen3.6-35B-A3B(source: AMD lemonade)
将Qwen3.6-35B-A3B接入opencode, 可以在断网运行的情况下直接翻译。我将新概念英语第四册皇家间谍篇拿来做测试，除了措辞不如北外教授的译文文雅外，意思基本到位。未来的AI PC部署可以考虑这一个记录。

笔记本+本地模型
最终部署结果：Qwen3:8b
因为笔记本电脑CPU有限，只能部署一个很小的模型，能力也很有限，接入opencode后效果不佳。所以我的操作是直接通过Ollama pull Qwen3:8b，Ollama run Qwen3:8b在命令行中直接执行操作。这个小模型的思考也会很长，翻译三行的英文，思考部分运行了两个满屏。所以我让云模型Deepseek-4v-flash帮我写了一个脚本，运行的时候能够指定目标语言和是否显示思考过程，还有计时。

## Unlimited OCR
百度推出的一个模型，据说超过MinerU.
问了opencode，两台电脑都不能部署。需要NVIDIA GPU。目前还没有使用场景，暂时不部署。

## VS Code 使用感悟
码农们可能不觉得，但是我第一次接触这个工具的时候觉得好用极了！

*本博客更新频率预计本周一篇*
*同名博客:kslizhong.cn / my-profile-website.pages.dev*



