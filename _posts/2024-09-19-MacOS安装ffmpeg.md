---
layout: post
category: "ffmpeg"
title: "MacOS安装ffmpeg"
tags: [ffmpeg, MacOS Software]
---

`homebrew`安装太慢了。

### 使用静态编译的 FFmpeg 二进制文件

你可以直接下载 FFmpeg 的预编译二进制文件，而无需通过 Homebrew 安装。这样可以避免编译时间，速度更快。

#### 步骤：

1.  访问 FFmpeg 的 [预编译二进制文件下载页面](https://ffmpeg.org/download.html) ，选择适用于 macOS 的预编译文件。
2.  下载并解压缩。
3.  将解压后的 `ffmpeg` 可执行文件移动到系统的 PATH 路径中，例如 `/usr/local/bin`，以便全局使用。

```shell
sudo mv ffmpeg /usr/local/bin/
```

这样，你就可以在终端中使用 FFmpeg 了。

