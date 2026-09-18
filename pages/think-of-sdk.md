---
level: 2
transition: none
# layout: two-cols-header
---

## XRアプリ開発における「ネイティブSDK」という選択肢

<br/>

<!-- ::left:: -->

XRプラットフォーマーがネイティブ向けのSDKを提供することが多くなってきた

- visionOSにおけるSwiftUIやReality Composer
- Meta HorizonOSにおけるMeta Spatial SDK
- AIグラス文脈でのネイティブSDK配布

<img src="/images/developing.png" class="h-70 mt-3"/>

---
level: 2
---

## UI開発におけるComposeの優位性

<br/>

Unityでの空間的なUI開発と比べたとき

- モバイルアプリ開発で培われてきたモダンなUI設計やエコシステムを取り入れられる
  - Composeが採用する宣言的UIやリアクティビティ
- ビルド時間短縮によるイテレーションの高速化
  - ホットリロードにも対応
- 柔軟なデザインシステムによるカスタマイズ
- AIによるコーディング支援との相性が良い

→ **UIが主体の3D/XRアプリ開発における優位性**

---
level: 2
---

## 複雑な制御をする3Dシーンを要する場合

<br/>

- 現状のSceneCoreには柔軟な3D操作のAPIがない
  - あくまでシンプルなSurfaceや3Dモデルをそのまま出すイメージ
  - グラフィクスやレンダリングに関する部分はあまり触れない（Cubeを出すなど）
- 3Dシーンのオーサリングの仕組みがない
  - DCCツールでglTFモデルを調整するイメージ
  - visionOSアプリ開発におけるReality Composer Proのようなものは必要そう
  - Unityで作ったほうが良い可能性が高い
