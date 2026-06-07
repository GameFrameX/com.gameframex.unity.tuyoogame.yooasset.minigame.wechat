<div align="center">

<img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />

# Game Frame X YooAsset MiniGame WeChat

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/blob/main/LICENSE.md)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/releases)
[![Unity Version](https://img.shields.io/badge/Unity-2019.4-black?logo=unity)](https://unity.com/)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

獨立遊戲前後端一體化解決方案 · 獨立遊戲開發者的圓夢大使

<br />

[文檔](https://gameframex.doc.alianblank.com) · [快速開始](#quick-start) · QQ群: 467608841 / 233840761

<br />

[English](README.md) | [简体中文](README.zh-CN.md) | **繁體中文** | [日本語](README.ja.md) | [한국어](README.ko.md)

</div>

## 項目簡介

GameFrameX 的 YooAsset 微信小遊戲運行時組件，面向 Unity WebGL 平台，提供與微信小遊戲文件系統、資源包加載流程的適配實現。

## 功能特性

- 提供微信小遊戲專用的 IFileSystem 實現
- 適配微信小遊戲 SDK 的 AssetBundle 下載與緩存流程
- 支持包版本請求、清單加載、資源包下載與加載
- 可對接遠程服務與解密服務

## 運行環境

- Unity 2019.4
- 平台：UNITY_WEBGL
- 條件編譯：WECHATMINIGAME
- 依賴：YooAsset、StarkWebGL、WXWebGL

## 快速開始

### 安裝

### 安裝

編輯 Unity 專案的 `Packages/manifest.json`，添加 `scopedRegistries` 部分：

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

`scopes` 控制哪些套件透過此註冊表解析。只有以 `com.gameframex` 開頭的套件才會從這個註冊表取得。

Then add the package to `dependencies`:

```json
{
  "dependencies": {
    "com.gameframex.unity.tuyoogame.yooasset.minigame.wechat": "1.0.0"
  }
}
```


## 使用範例

1. 確保已接入微信小遊戲 SDK，並啟用 `WECHATMINIGAME` 宏
2. 通過 `WechatFileSystemCreater.CreateFileSystemParameters(...)` 生成文件系統參數
3. 將參數傳入 YooAsset 的文件系統創建流程
4. 按照 YooAsset 的常規流程進行初始化、版本請求、清單加載與資源加載

## 主要類型

- `WechatFileSystem`：微信小遊戲文件系統實現
- `WechatFileSystemCreater`：文件系統參數構建入口
- `LoadWechatAssetBundleOperation`：資源包下載與加載操作
- `UnityWechatAssetBundleRequestOperation`：基於微信小遊戲 SDK 的下載請求封裝

## 注意事項

- 需要設置微信小遊戲的緩存根目錄，否則會拋出異常
- 未配置遠程服務時會回退到 Web 服務器路徑
