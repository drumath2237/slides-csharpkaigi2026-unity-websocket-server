---
level: 2
transition: none
---

## XR SDKに関する情報源

<br/>

- Developers Guide
  - https://developer.android.com/develop/xr/jetpack-xr-sdk
- Release Notes
  - https://developer.android.com/jetpack/androidx/releases/xr-compose
- API Reference
  - https://developer.android.com/reference/kotlin/androidx/xr/compose/platform/
- 実際のコード

---
level: 2
layout: two-cols
---

## XR SDKの中身を見てみる

<br/>

Jetpack全体のコードは公開されている

<span style="font-size:17px;">
<a href="https://android.googlesource.com/platform/frameworks/support/">
https://android.googlesource.com/platform
/frameworks/support/
</a>
</span>

Googleが独自で持っている  
リモートリポジトリホスティングサービス

`xr/`というフォルダの中がXR SDK

::right::

<img src="/images/support.png" />

---
level: 2
layout: two-cols
---

## Jetpack Compose for XR

namaspace: `androidx.xr.compose`  
latest: `1.0.0-alpha8` (2025/10/22)

---

Jetpack Composeを使って空間UIを実装するためのライブラリ

Android XRで空間パネルに表示するUIに必要な部品を提供

- `Subspace`コンポーザブルの定義
- Subspace Composables
- Spatialized Component
- Subspace Modifier

::right::

<div class="ml-10">

<img src="/images/subspaceorbiter.png" class="mt-10"/>

<span style="font-size:12px;">
Full SpaceでSpatialPanelとOrbiterがレンダリングされている
<br/>
https://developer.android.com/develop/xr/jetpack-xr-sdk/develop-ui
</span>

</div>

---
level: 2
layout: two-cols
---

## Material Design for XR

namespace: `androidx.xr.compose.material3`  
latest: `1.0.0-alpha12` (2025/10/22)

---

Googleが提供するMaterial Designを  
空間UIで扱うするためのライブラリ

分けて取り上げられがちだが、  
実態としてはCompose for XRの一部

Material Designでは  
様々な画面サイズのデバイスに対応すべく  
Adoptive Layoutという仕組みが用意されている

::right::

<img src="/images/nonspatialized.png" class="h-50 ml-10">
<img src="/images/spatializedrail.png" class="h-50 ml-10 mt-5">

<span style="font-size:10px;">https://developer.android.com/develop/xr/jetpack-xr-sdk/material-design</span>

---
level: 2
layout: two-cols
---

## Material Design for XR

<br/>

Material Designでは  
様々な画面サイズのデバイスに対応すべく  
Adoptive Layoutという仕組みが用意されている

`EnableXrComponentOverrides`  
というコンポーザブルの子にすると  
Material3のコンポーネントはSpatial UIに対応するように

Material Design Guidelineには  
「XR」の項目が盛り込まれている（すごい）

::right::

<div class="ml-5 mt-10">
<img src="/images/materialbar.png"/>
<a href="https://m3.material.io/components/navigation-bar/xr">
https://m3.material.io/components/navigation-bar/xr
</a>
</div>

---
level: 2
layout: two-cols
---

## Jetpack SceneCore

namespace: `androidx.xr.scenecore`  
latest: `1.0.0-alpha9` (2025/11/19)

---

3Dシーン上のオブジェクトを扱うための低レベルな機能を提供するライブラリ

空間UIのパネルや3Dモデル、3D環境といったものをEntityとして管理する  
空間音響や空間ビデオの再生などの機能も

Entity-Component Systemを採用

::right::

<div class="ml-10">

<img src="/images/3dmodel.png" />

<span style="font-size:15px;">エミュレータ内で3Dモデルをロードして表示する様子</span>
</div>

---
level: 2
layout: two-cols
---

## ARCore for Jetpack XR

namespace: `androidx.xr.arcore`  
latest: `1.0.0-alpha08` (2025/11/19)

---

AR機能を扱うためのライブラリ

従来からモバイルで使われている  
ARCore SDK for Androidとは別物だけど  
内部的にそれに依存している

現在エミュレータでは動かない

::right::

<div class="ml-10 mt-10">

<img src="/images/hand.png"  />

<span style="font-size:11px;">
https://developer.android.com/develop/xr/jetpack-xr-sdk/arcore/hands
</span>

</div>

---
level: 2
---

## XR Runtime

namespace: `androidx.xr.runtime`  
latest: `1.0.0-alpha08` (2025/11/19)

---

XR SDK全体で使えるデータ型やヘルパーの定義

`Vector3`や`Ray`などの基本的な型

`XrDevice`や`Session`といったXRの基礎的なデータ

---
level: 2
---

## パッケージ全体の構造と依存関係

<img src="/images/packagestru.png" class="h-110"/>

---
level: 2
layout: two-cols
---

## Jetpack Composeによる

## UIの構築

<br/>

コンポーザブルと呼ばれる部品を組み合わせて  
UIを構築するためのフレームワーク

宣言的UIの思想に基づいており、  
モダンなAndroid開発ではよく使われる

Kotlin言語で開発可能

---

コンポーザブル関数のイメージ

```kotlin
@Composable
fun ExampleButton(onClick: () -> Unit) {
    Button(onClick = { onClick() }) {
        Text("Hello")
    }
}
```

::right::

<div class="ml-30" style="text-align:center;">

<img src="/images/jetpacklogo.png"　class="h-65" style="display:inline;"/><br/>
<span style="font-size:15px;">Composeのロゴ</span>

</div>

---
level: 2
layout: two-cols-header
---

::left::

<div class=" ml--10">

```kotlin
@Composable
fun Example2DComposable() {
    var label by remember { mutableStateOf("") }

    Surface {
        Column(
            modifier = Modifier.padding(48.dp),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Text(label)
            Row(
                modifier = Modifier.fillMaxSize(),
                horizontalArrangement = Arrangement.Center
            ) {
                Button(
                    onClick = { label = "button 1" },
                    modifier = Modifier.padding(5.dp)
                ) { Text("Button 1") }
                Button(
                    onClick = { label = "button 2" },
                    modifier = Modifier.padding(5.dp)
                ) { Text("Button 2") }
            }
        }
    }
}
```

</div>

::right::

<img  src="/images/composable.png" class="ml-10 h-115"/>

---
level: 2
layout: two-cols-header
---

## Full SpaceモードのUI

::left::

<br/>

Full Spaceで動作するコンポーザブルは  
`Subspace`コンポーザブルの子である必要がある

```kotlin
@Composable
fun SpatialExample() {
    // Full Spaceで動作する特殊なコンポーザブル
    Subspace {
        SpatialPanel(
            modifier = SubspaceModifier.width(400.dp)
        ) {
            Example2DComposable()
        }
    }
}
```

::right::

<div class="ml-10 mt-10 mr--5">

<img  src="/images/spatialized.png" />

Subspaceコンポーザブルで囲むことで  
Full Spaceでも動作するように

</div>

---

level: 2
layout: two-cols
---

## Spatial Component

<br/>

Spatial Popupのようなコンポーネントは  
`elevation`をModifierで指定して  
高さを出せる

```kotlin
SpatialPopup(
    alignment = Alignment.TopCenter,
    elevation = 78.dp // 任意の値
) {
    Button({}) { Text("Spatial Popup") }
}
```

::right::

<img src="/images/spatialpopup.png" class="ml-5 mt-10"/>

---
level: 2
layout: two-cols-header
---

## SceneCoreによる3D空間体験の実装

::left::

<br/>

Jetpack SceneCoreは空間UIのパネルなどを含む、  
あらゆる3D表現を扱う低レベルなAPIを提供

Entity-Component Systemを採用

空間パネルや3Dモデルだけでなく、  
環境マップや空間ビデオ、空間音響に関する機能も含まれる

---

3Dモデルの表示

<div class="mr--45">

```kotlin
val session = LocalSession.current

LaunchedEffect(null) {
    if (session != null) {
        val gltfModel = GltfModel.create(session, Paths.get("models", "Fox.glb"))
        val entity = GltfModelEntity.create(session, gltfModel)
        entity.setScale(0.005f)
    }
}
```

</div>

::right::

<img src="/images/fox.png" class="ml-10 mt-10" style="z-index:20;display:block"/>

---
level: 2
layout: two-cols
---

## ARCoreによるAR機能の実装

<br/>

例えばDepth estimation

Depthの動作モードを設定

```kotlin
val newConfig = session.config.copy(
    depthEstimation
        = Config.DepthEstimationMode.SMOOTH_ONLY,
)
```

比較的シンプルなAPIでDepth値の取得

```kotlin
// Depth Map取得
val depthMap = DepthMap.left(session) ?: return

// 深度値の取得
val result = depthMap.smoothDepthMap?.get(index)
```

::right::

<div class="ml-5">
<img src="/images/Depth.png" />
Depth estimationの結果
<span style="font-size:15px;">
<a href="https://developer.android.com/develop/xr/jetpack-xr-sdk/arcore/depth">
https://developer.android.com/develop/xr/jetpack-xr-sdk/arcore/depth
</a>
</span>
</div>

---
level: 2
layout: two-cols
---

## ARCoreによるAR機能の実装

<br/>

例えばPlane detection

検知委平面の設定

```kotlin
val newConfig = session.config.copy(
    planeTracking =
    Config.PlaneTrackingMode.HORIZONTAL_AND_VERTICAL,
)
```

State Flowとして検知平面の取得

```kotlin
Plane.subscribe(session).collect { planes ->
    plane.type
    // HORIZONTAL_DOWNWARD_FACING, VERTICAL, ...

    plane.label
    // CEILING, FLOOR, TABLE, ...
}
```

<!-- ::right:: -->

---
level: 2
layout: two-cols
---

## ARCoreでサポートされる機能

<br/>

ドキュメント曰く

- Plane
- (Hit-Test)
- Anchors
- Hand tracking
- Head tracking
- Face tracking
- Depth estimation

実際のコードを見ると、  
Eye trackingやGeospatial APIなども  
見受けられる

::right::

<img src="/images/arcorefeature.png" class="h-120 ml-10"/>
