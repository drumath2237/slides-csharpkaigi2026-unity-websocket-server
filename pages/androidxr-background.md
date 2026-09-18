---
level: 2
transition: none
---

## Android XRのこれまでの流れ

<br/>

|               |                          |                                               |
| :------------ | :----------------------- | :-------------------------------------------- |
| 2024/12/12    | Android XR発表           | Introducing Android XR SDK Developer Preview  |
| 2025/05/20-21 | Google I/O 2025          | KeynoteではARグラスを使ったライブデモもあった |
| 2025/10/22    | SamsungからGalaxy XR発表 | 初のAndroid XR OS搭載デバイス                 |

<br/>

<img src="https://storage.googleapis.com/gweb-uniblog-publish-prod/images/0098-ARVR-XR-Blog-Header-2096x11.width-1600.format-webp.webp" class="h-40"/>
<img  src="https://img.global.news.samsung.com/global/wp-content/uploads/2024/12/Samsung-Mobile-XR-Project-Moohan-Android-XR-platform-Google_main1.jpg" class="h-40 ml-10"/>

<br/>

<span style="font-size:10px;">
https://blog.google/products/android/android-xr/<br/>
https://news.samsung.com/global/unlock-the-infinite-possibilities-of-xr-with-galaxy-ai
</span>

<style>
img {
  display: inline;
}
</style>

---
level: 2
layout: two-cols-header
---

::left::

## Google I/O 2025

<!-- <br/> -->

１年に１回のGoogle公式技術カンファレンス

KeynoteにてARグラスを使ったライブデモ

その他にも２，３本  
Android XR関連のセッションがあった

<img src="/images/googleiodemo.png" h-55/>

https://youtu.be/o8NiE3XMPrM

::right::

## Galaxy Event October 2025

<!-- <br/> -->

Samsung社のイベント

Project Moohanという名前だったものが  
正式にGalaxy XRとして発表

<br/>

<img src="/images/galaxyxrsession.png" h-60/>

https://youtu.be/ITXJquX9FqM

---
level: 2
layout: two-cols
---

## Android XRとは何か

<br/>

XRデバイスに向けの**OS**

HMDやグラスなど、  
様々なデバイスタイプに対応している

ARCoreやGoogle Lens、  
Googleマップなどのアプリ、Geminiなどを搭載

SamsungやQualcommと協力

::right::

<div class="ml-10">
  <img src="/images/moohan.png" />
  <span style="font-size:15px;">https://www.youtube.com/watch?v=Pn5uG1ys-pE</span>
</div>

---
level: 2
layout: two-cols
---

## Android XRで動作するアプリ

<br/>

アプリには2種類の状態がある

- Home Space
- Full Space

一般的にスマホで使えるアプリは  
Home Spaceで動作可能

Android XR向けにcapabilityの設定や  
Spatial UIが構築されていれば  
Full Spaceで動作

2つの状態は相互に遷移可能  
UnityだとFull Spaceしか使えないなどの制約も

<br/>

（手元のシミュレータで動作させた様子→）

::right::

<img src="/images/clock2d.png" class="ml-30 h-65 mt--7"/>

<img src="/images/codelabspatial.png" class="ml-30 h-65 mt-3"/>

---
level: 2
---

## 開発環境

<br/>

アプリ開発の選択肢は次のとおり

- Jetpack XR SDK
  - Kotlin/Composeを使うネイティブSDK（詳細はこれから）
- Unity
  - XRIやARFoundation、OpenXR Pluginなどを使って開発
  - Android XR Extentions for Unityをインポートして使う
- OpenXR
  - OpenXR 1.0, 1.1の規格に従っている
- WebXR
  - Chrome for Android XRなどのブラウザで動作するWebXRアプリ開発
  - WebXR Device APIを使う
