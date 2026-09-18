---
# You can also start simply with 'default'
theme: default
title: Jetpack XR SDKから紐解くAndroid XR開発と技術選定のヒント
info: XR Kaigi 2025の登壇資料
author: にー兄さん@drumath2237
class: text-left
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
fonts:
  sans: M PLUS 2
  mono: JetBrains Mono
layout: intro
hideInToc: true
download: true
export:
  dark: true
exportFilename: XRK2025-S-045_堤海斗
transition: none
---

# <span style="color:#33CCFF;">Jetpack XR SDK</span>から紐解く

# Android XR開発と

# 技術選定のヒント

### にー兄さん[@ninisan_drumath](https://twitter.com/ninisan_drumath)

### XR Kaigi 2025

---
layout: two-cols
hideInToc: true
---

## にー兄さん

ソフトウェアエンジニア@HoloLab inc.

- Babylon.js勉強会運営
- Iwaken Lab.
- Microsoft MVP for  
  Developer Technologies (2024~)

<br/>

### 好きな技術

Babylon.js / WebXR Device API /  
Android XR / 3D Gaussian Splatting

- <uim-twitter-alt /> [@ninisan_drumath](https://x.com/ninisan_drumath)
- <uim-github-alt /> [@drumath2237](https:github.com/drumath2237)

::right::

<img src="https://pbs.twimg.com/profile_images/1113849253548269568/4uy_K_LA_400x400.png" class="rounded h-60 ml-20"/>
<img src="/images/realavatar.jpg" class="rounded h-60 ml-50"/>

---
hidenToc: true
layout: section
---

## 本日の資料は撮影・SNS共有OKです📸

<br/>

## （のちほど公開します）

---
hideInToc: true
---

## 本日のお話

<br/>

「Jetpack XR SDK」がメイン

Android XRを取り巻く状況やSDKの概要

特にSDKが（現状）どのような機能を持っており、  
どんな目的で使えるものなのか

XR SDKの得意・苦手、使い分けについて

## ゴール

<br/>

- Android XRに興味のあるエンジニアがJetpack XR SDKについて知る
- Android XRアプリ開発時の技術選定について解像度を高める
  - 例えばUnityとどっちを使うか、など

---
hideInToc: true
---

## 本セッションにおける検証環境

<br/>

- Windows 11 Home
- Android Studio Otter 3 Feature Drop | 2025.2.3 Canary 2
- Android Emulator 36.4.1
  - Google Play XR Intel x86_64 Atom System Image Revision 7
- Jetpack XR SDK
  - Jetpack Compose for XR 1.0.0-alpha08
  - Material Design for XR 1.0.0-alpha12
  - Jetpack SceneCore 1.0.0-alpha09
  - ARCore for Jetpack XR 1.0.0-alpha08

---
hideInToc: true
---

## アジェンダ

<br/>

<Toc maxDepth="1"/>

---
layout: section
---

# Android XRに関する背景

---
src: ./pages/androidxr-background.md
---

---
layout: section
title: Jetpack XR SDKを使ったアプリ開発
---

# Jetpack XR SDKを使った

# アプリ開発

---
src: ./pages/develop-with-xrsdk.md
---

---
layout: section
title: Deep Dive into XR SDK
---

# Deep Dive into XR SDK

---
src: ./pages/deep-dive-into-sdk.md
---

---
layout: section
title: XR SDKから考察するAndroid XRアプリ開発
---

# XR SDKから考察する

# Android XRアプリ開発

---
src: ./pages/think-of-sdk.md
---

---
layout: section
---

# おわりに

---
level: 2
---

## まとめ

<br/>

Android XRアプリのネイティブSDKであるJetpack XR SDK

Kotlin / Composeによるアプリ開発ができるため、  
宣言的UIやリアクティブプログラミングの良さを生かしたUI開発ができる

高度な3Dデータの操作はまだできないため  
複雑なゲームなどはUnityでやるのが良い

UI主体ならネイティブ、ゲームのようなものはゲームエンジン  
→ これって**普通の考え方なのでは？**

いままで「XRと言えばUnity」だった世界から  
要件によって適切な技術選定が必要になってきている

---
level: 2
---

## 関連・参考

<br/>

- Android XR (Android Developer)  
  https://developer.android.com/develop/xr
- Develop with the Jetpack XR SDK  
  https://developer.android.com/develop/xr/jetpack-xr-sdk
- Android Studio tools for XR  
  https://developer.android.com/develop/xr/jetpack-xr-sdk/studio-tools
- android/xr-samples (GitHub)  
  https://github.com/android/xr-samples
- The future is now, with Compose and AI on Android XR (Google I/O 2025)  
  https://io.google/2025/explore/technical-session-2
- 『Jetpack XR SDKによるAndroid XRアプリ開発の現状整理』  
  https://techbookfest.org/product/3Ttz8QVn4A5uXRYyRm34Xr?productVariantID=fArCdYsZCt0d8ez5nsFNj9
