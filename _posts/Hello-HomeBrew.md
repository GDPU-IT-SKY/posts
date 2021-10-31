---
title: Homebrew 入门教程
date: 2021-10-31 23:09:07
author: Supdrewin
hidden: false
tags: macOS
---

### 什么是 Homebrew

`Homebrew` 是一个基于 `git` 和 `ruby` 的软件包管理器, 适用于 `macOS` 及 `Linux`.

### 安装 Homebrew _- 此处以 `macOS` 为例_

1. 使用安装脚本 _- 由于地理位置, 此处使用 `jsDelivr CDN` 以加速下载._

   ``` shell
   /bin/bash -c "$(curl -fsSL https://cdn.jsdelivr.net/gh/Homebrew/install@HEAD/install.sh)"
   ```
2. 设置远程上游 _- 将远程上游设置为 `科大源`, 以获得良好的网速体验._

   一般情况下 `macOS` 的 `默认 Shell` 为 `zsh`, 所以我们将环境变量写入 `zsh` 的用户配置文件.

   ``` shell
   echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"' >> ~/.zshrc
   echo 'export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles"' >> ~/.zshrc
   echo 'export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.ustc.edu.cn/homebrew-core.git"' >> ~/.zshrc
   ```

   以下设置大型二进制包 _(或 `macOS` 应用)_ 的远程.

   ``` shell
   brew tap --custom-remote --force-auto-update homebrew/cask https://mirrors.ustc.edu.cn/homebrew-cask.git
   brew tap --custom-remote --force-auto-update homebrew/cask-versions https://mirrors.ustc.edu.cn/homebrew-cask-versions.git
   ```

3. 更新源列表
   ``` shell
   brew update
   ```

### Homebrew 的基本用法

- 搜索名为 `text` 或匹配 `text` 的软件包
  ``` shell
  brew search text
  brew search /text/
  ```

- 安装名为 `package` 的软件包:

  ``` shell
  brew install package
  ```

- 卸载名为 `package` 的软件包:

  ``` shell
  brew uninstall package
  ```

- 列出所有安装的软件包:

  ``` shell
  brew list
  ```

- 刷新软件源列表

  ``` shell
  brew update
  ```

<!-- 作者的 macOS 正在重装的路上, 未完待续 -->

_Tips: 若要获得详细的过程输出, 可以在命令中加上 `--verbose` 或 `-v`._

### 参考链接

- [Homebrew 官方主页](https://brew.sh/index_zh-cn "中文主页")
- [LUG@USTC 镜像说明](https://mirrors.ustc.edu.cn/help/brew.git.html "brew.git")
