# Known Issues & Limitations

## Known Issues

### Apply 後に Prefab を unpack する / Armature を変更する

!!! warning
    **Apply** 実行後のアバターに対して、Prefab の unpack や Armature の手動編集を行う場合は注意してください。

過去のバージョンでは、Prefab を unpack すると  
非表示オブジェクト **__InertiaBonesEditorData** に保存されたバックアップ参照が破損する場合がありました。

現在は安全対策が追加されており、Debug / Maintenance 内の修復ボタンでバックアップを再構築できます。

ただし、ツール適用後に Armature 構造を変更することは  
基本的に想定されたワークフローではありません。

---

## Known Limitations

### Converted Source Bone 下の PhysBone チェーン

現在のバージョンでは、

**InertiaBones の揺れは別の PhysBone チェーンには伝播しません。**

例：

```
Upperleg_R
├── Lowerleg_R
└── Belt_PB_R  <-- Has PhysBone
    └── Belt_PB_001_R
```

この制限は将来のアップデートで改善予定です。

---

!!! info
    回避策として、PhysBone チェーンを対応する **_Jiggle** ボーンに親付けすることができます。

!!! warning
    この方法は推奨ワークフローではありません。  
    使用する場合はアバターのバックアップを作成してください。