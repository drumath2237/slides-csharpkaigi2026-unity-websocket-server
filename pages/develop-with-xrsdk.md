---
level: 2
transition: none
---

## Jetpack XR SDKとは何か

<br/>

Android XRで動作するような  
没入体験を有するアプリケーションを開発するためのライブラリ群

いままでのAndroidアプリ開発と同じように  
KotlinやCompose、Android Studioといったツールを使える

主に次の4つのパッケージから構成される

- Jetpack Compose for XR
- Material Design for XR
- Jetpack SceneCore
- ARCore for Jetpack XR

---
level: 2
layout: two-cols-header
---

## Android Studioとエミュレータの利用

::left::

<br/>

モバイルアプリ開発などと同様に、  
Android Studioなどのツールを活用可能

- ビルド、テスト、デバッグなど
- Home SpaceでのUIはAndroid Studio内で  
  プレビューしながら作れる

Android XR emulatorが用意されており、  
Compose for XRやSceneCoreを使った  
機能の動作を確認できる

エミュレータの仕組みで  
2D UIはホットリロードも可能

::right::

<div class="mt-15 ml-0 mr--10" style="z-index:10;">

<img src="/images/developing.png" />

<!-- <img src="/emu.png" class="h-50 ml-7 mt--10" style="z-index:30;"> -->
</div>

---
level: 2
layout: two-cols
---

## 開発の始め方

<br/>

### ■XRのテンプレートから作成

Android Studioのテンプレートから  
XRカテゴリのものを使用する

ComposeによるシンプルなUI実装と  
Spaceモードの切り替えが実装されている

### ■XR Samplesを改変

GitHubにあがっている  
公式のサンプルプロジェクトを改変する方法

空間UIやState管理、3Dモデル表示など  
比較的作りこまれている

https://github.com/android/xr-samples

::right::

<div class="ml-5 mt--5">
<img src="/images/xrtemplate.png"/>
<img src="/images/xrsamples.png" class="h-60 mt-5"/>
</div>
