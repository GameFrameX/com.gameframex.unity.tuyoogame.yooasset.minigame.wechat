<div align="center">

<img src="https://download.alianblank.com/gameframex/gameframex_logo_320.png" alt="Game Frame X Logo" width="160" />

# Game Frame X YooAsset MiniGame WeChat

[![License](https://img.shields.io/github/license/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/blob/main/LICENSE.md)
[![Version](https://img.shields.io/github/v/release/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat)](https://github.com/GameFrameX/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat/releases)
[![Unity Version](https://img.shields.io/badge/Unity-2019.4-black?logo=unity)](https://unity.com/)
[![Documentation](https://img.shields.io/badge/Documentation-docs-blue)](https://gameframex.doc.alianblank.com)

インディゲーム開発者向けオールインワンソリューション · インディ開発者の夢を支援

<br />

[ドキュメント](https://gameframex.doc.alianblank.com) · [クイックスタート](#quick-start) · QQグループ: 467608841 / 233840761

<br />

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | **日本語** | [한국어](README.ko.md)

</div>

## プロジェクト概要

GameFrameX の YooAsset WeChat ミニゲームランタイムコンポーネント。Unity WebGL プラットフォーム向けに、WeChat ミニゲームのファイルシステムとアセットバンドル読み込みワークフローの適配実装を提供します。

## 機能特性

- WeChat ミニゲーム専用の IFileSystem 実装を提供
- WeChat ミニゲーム SDK の AssetBundle ダウンロードおよびキャッシュワークフローに対応
- パッケージバージョンリクエスト、マニフェスト読み込み、アセットバンドルのダウンロードと読み込みをサポート
- リモートサービスおよび復号サービスとの連携に対応

## 動作環境

- Unity 2019.4
- プラットフォーム：UNITY_WEBGL
- 条件コンパイル：WECHATMINIGAME
- 依存関係：YooAsset、StarkWebGL、WXWebGL

## インストール方法（いずれかを選択）

1. `manifest.json` の `dependencies` に追加：
   ```json
   {
     "com.gameframex.unity.tuyoogame.yooasset.minigame.wechat": "https://github.com/gameframex/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat.git"
   }
   ```
2. Unity の Package Manager で Git URL を使用して追加：
   https://github.com/gameframex/com.gameframex.unity.tuyoogame.yooasset.minigame.wechat.git
3. リポジトリを直接ダウンロードして Unity プロジェクトの `Packages` ディレクトリに配置

## 使用方法

1. WeChat ミニゲーム SDK が統合され、`WECHATMINIGAME` マクロが有効になっていることを確認
2. `WechatFileSystemCreater.CreateFileSystemParameters(...)` でファイルシステムパラメータを生成
3. パラメータを YooAsset のファイルシステム作成ワークフローに渡す
4. YooAsset の標準ワークフローに従って初期化、バージョンリクエスト、マニフェスト読み込み、アセット読み込みを行う

## 主要タイプ

- `WechatFileSystem`：WeChat ミニゲームファイルシステム実装
- `WechatFileSystemCreater`：ファイルシステムパラメータビルダーエントリポイント
- `LoadWechatAssetBundleOperation`：アセットバンドルのダウンロードと読み込み操作
- `UnityWechatAssetBundleRequestOperation`：WeChat ミニゲーム SDK ベースのダウンロードリクエストラッパー

## 注意事項

- WeChat ミニゲームのキャッシュルートディレクトリを設定する必要があります。設定しない場合、例外がスローされます
- リモートサービスが設定されていない場合、Web サーバーパスにフォールバックします
