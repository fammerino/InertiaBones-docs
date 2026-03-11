# Configuration settings

## UI Explanation

![UI Screenshot](assets/UIScreenshot.PNG)

### Header buttons

- **Docs**  
  現在表示しているドキュメントページを開きます。

- **Options**  
  グローバル設定が配置される場所です。

---

## Avatar Root / Bones

- **Avatar Root**  
  操作対象のアバターを指定します。

- **Bones**  
  処理を行う **Source Bone** を追加するリストです。

例：

- UpperLeg
- LowerLeg

### Category

インフルエンススライダーで使用されるカテゴリです。  
多くの場合は自動検出されますが、必要に応じて手動で変更できます。

### Add Bone Slot / Remove

ボーンスロットの追加または削除を行います。

### Clear Empty Slots

Source Bone が **None** のスロットを削除します。

---

## Processing

### Bake converted meshes as assets

次のモードを切り替えます。

**Session Mode**

- メッシュはメモリ上のみで変更
- プロジェクト再起動で消える

**Persist (Bake) Mode**

- メッシュをアセットとして保存
- Prefab-safe

---

### Include Inactive Objects

Hierarchy 内で非アクティブなオブジェクトも対象にします。

例：

- 非表示の衣装メッシュ

---

### Match outfit meshes by bone name

通常は **ON（推奨）** にします。

これにより、追加の衣装アーマチュアに余分なコントローラーが作成されるのを防ぎます。

---

## Weight Mode

メッシュウェイトの書き換え方法を決定します。

### Replace (Standard)


Source Bone → Jiggle Bone


すべてのウェイトを Jiggle に移動します。

### Split

Source と Jiggle の間でウェイトを分割します。

---

## Presets

**Built In** または **Custom** を選択できます。

Custom プリセット保存場所：


Assets/Corner22/InertiaBonesData/Presets/Custom


### Built In Presets

現在のプリセットは次のカテゴリがあります。

**Rotational**

- 単一軸回転の PhysBone

**Angle**

- 通常の PhysBone 挙動  
- Max Angle をかなり低くする必要があります

---

## Hinge / Max Angle

- **Use Hinge Limit (Axis Lock)**  
  Rotational では ON、Angle では OFF

- **Hinge Axis**  
  ヒンジの回転軸

- **Max Angle**  
  PhysBone の Max Angle

---

## Endpoint

!!! tip
    Endpoint の長さは PhysBone の揺れ方に影響する場合があります。

### Endpoint Position

通常は **X方向に延長** します（Hinge Axis が Y の場合）。

### Endpoint X Sign Mode

次のモードがあります：

- Mirror
- Invert
- Manual

---

## Dynamics (Base)

PhysBone コンポーネントと同様の設定です。

!!! info
    **Advanced（Momentum）** を使用することを推奨します。

また、次の設定を推奨します：


Immobile Type: World Experimental


これにより移動時の不要な揺れを抑えられます。

---

## Category Influence Settings

Bones リストで設定されたカテゴリごとに  
PhysBone の影響量を調整するスライダーです。

通常は **高めの値** を推奨します。

低すぎると揺れが非常に硬くなります。

---

## Optional Upload Copy

変更を現在のアバターではなく  
**複製された Upload 用アバター** に適用します。

---

## Reset UI / Run

- **Reset UI (Session)**  
  UI を初期状態に戻します

- **Run Apply / Remove**  
  現在選択されている Mode に応じて処理を実行します

---

## Debug / Maintenance

ツールのバックアップデータの管理やデバッグ用機能です。

### Clean Old Baked Meshes (Keep Last 2)

使用されていない古い GeneratedMeshes を削除します。

### Repair Backup References

バックアップ参照を修復します。

### Reveal Editor Data Root

非表示の `_InertiaBonesEditorData` を表示します。

### Hide Editor Data Root

再び非表示にします。