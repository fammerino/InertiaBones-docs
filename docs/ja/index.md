# InertiaBones

InertiaBones は、VRChat アバター向けの Unity Editor ツールです。

任意のアバターの任意のボーンに対して、**回転ベースの PhysBone の揺れ（ジグル）** を簡単に追加できます。

通常、Unity 内で PhysBone 用のコントローラー構造を手動で構築し、メッシュウェイトを調整する作業は非常に時間がかかり、ミスも起こりやすいものです。  
InertiaBones はこの作業を自動化し、安全に試行錯誤できる環境を提供します。

---

## 主な機能

- 安定した PhysBone コントローラーチェーンの自動生成
- SkinnedMeshRenderer の安全なウェイト書き換え
- 非破壊で調整できる **Session モード**
- メッシュをアセットとして保存する **Bake モード**
- ウェイト影響の消失防止
- 古いベイクメッシュの自動クリーンアップ

このツールは、現在および今後追加される機能のためのフレームワークとして設計されています。  
そのため、任意の場所に PhysBone のダイナミクスを追加することができます。

!!! info
    初期リリースのため、まだ見つかっていないエッジケースが存在する可能性があります。  
    問題を見つけた場合は **Contact** セクションからバグレポートを送ってください。

[Get started →](quick-start.md){ .md-button .md-button--primary }
[Configuration →](configuration.md){ .md-button }

---

## Important Notes

InertiaBones が行う処理は、理論上は Unity 内で手動でも実現可能です。  
しかし正確に実行するには多くの手順が必要で、メッシュウェイトを直接変更する作業は特にミスが発生しやすくなります。

InertiaBones を使うことで：

- 数秒で複雑なコントローラー構成を生成
- 非破壊環境で自由に調整
- 最終的にメッシュを安全にアセット化

といったワークフローを簡単に実現できます。

このツールは次の安全設計で作られています：

- 既存のメッシュアセットを直接上書きしない
- 常にバックアップから再構築する
- ベイク済みアセットは変更しない
- 影響が残っているコントローラーの削除を防止
- bindpose の整合性を維持

---

## Core Workflow Model

各 **Source Bone** に対して、以下の構造が作成されます。



```
PBCTRL_SourceBone
└── SourceBone_Sim
    └── SourceBone_Jiggle
```


メッシュウェイトは次のように変更されます。

Source Bone → Jiggle Bone

すべての永続的な出力は、アバター内に保存される非表示のバックアップから生成されます。