<div align="center">

<img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />

# Game Frame X YooAsset MiniGame WeChat

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/blob/main/LICENSE.md)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/releases)
[![Unity Version](https://img.shields.io/badge/Unity-2019.4-black?logo=unity)](https://unity.com/)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

All-in-One Solution for Indie Game Development · Empowering Indie Developers' Dreams

<br />

[Documentation](https://gameframex.doc.alianblank.com) · [Quick Start](#quick-start) · QQ Group: 467608841 / 233840761

<br />

**English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md)

</div>

## Project Overview

GameFrameX YooAsset WeChat MiniGame runtime component for Unity WebGL, providing adapter implementations for the WeChat MiniGame file system and asset bundle loading workflow.

## Features

- Provides WeChat MiniGame-specific IFileSystem implementation
- Adapts WeChat MiniGame SDK AssetBundle download and caching workflow
- Supports package version requests, manifest loading, and asset bundle download and loading
- Compatible with remote services and decryption services

## Runtime Requirements

- Unity 2019.4
- Platform: UNITY_WEBGL
- Conditional compilation: WECHATMINIGAME
- Dependencies: YooAsset, StarkWebGL, WXWebGL

## Installation

### Installation

Edit your Unity project's `Packages/manifest.json` and add the `scopedRegistries` section:

```json
{
  "scopedRegistries": [
    {
      "name": "GameFrameX",
      "url": "https://gameframex.upm.alianblank.uk",
      "scopes": [
        "com.gameframex"
      ]
    }
  ]
}
```

`scopes` controls which packages are resolved through this registry. Only packages whose names start with `com.gameframex` will be fetched from it.

Then add the package to `dependencies`:

```json
{
  "dependencies": {
    "com.gameframex.unity.tuyoogame.yooasset.minigame.wechat": "1.0.0"
  }
}
```


## Usage

1. Ensure the WeChat MiniGame SDK is integrated and the `WECHATMINIGAME` macro is enabled
2. Use `WechatFileSystemCreater.CreateFileSystemParameters(...)` to generate file system parameters
3. Pass the parameters to YooAsset's file system creation workflow
4. Follow YooAsset's standard workflow for initialization, version requests, manifest loading, and asset loading

## Main Types

- `WechatFileSystem`: WeChat MiniGame file system implementation
- `WechatFileSystemCreater`: File system parameter builder entry point
- `LoadWechatAssetBundleOperation`: Asset bundle download and loading operation
- `UnityWechatAssetBundleRequestOperation`: Download request wrapper based on WeChat MiniGame SDK

## Notes

- The WeChat MiniGame cache root directory must be set, otherwise an exception will be thrown
- If no remote service is configured, it falls back to the web server path
