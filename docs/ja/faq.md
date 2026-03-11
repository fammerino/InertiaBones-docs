# FAQ

## 元のメッシュは変更されますか？

いいえ。

Persist モードでも  
既存のメッシュアセットは上書きされません。

---

## すでに PhysBones がある場合でも使えますか？

はい。

InertiaBones は **選択したボーンのみ** にコントローラーを追加します。

既存の PhysBone コンポーネントやチェーンはそのまま維持されます。

---

## すべて削除するには？

Mode を **Remove** に変更し

1. **Scan & Fill Existing Controllers**
2. **Remove**

を実行してください。

---

## "Mesh has no bones assigned" エラー

アバター階層に  
**ボーンを持たない静的メッシュ** が存在する場合に発生します。

対処方法：

- メッシュをアバター階層外へ移動
- または削除

---

## MA Scale Adjuster が元に戻る

InertiaBones はウェイトを書き換えるため  
MA Scale Adjuster のスケール処理がリセットされます。

回避策：

**MA Scale Adjuster** を  
**_Jiggle ボーン** に移動します。

!!! warning
    これは推奨ワークフローではありません。  
    使用する場合はバックアップを作成してください。

---

## Persist を複数回実行できますか？

はい。

実行するたびに新しいメッシュアセットが生成されます。

---

## ベイクされたメッシュの保存場所

Assets/Corner22/InertiaBonesData/GeneratedMeshes/Avatar-name/

ユーザーデータはツール本体とは別フォルダに保存されます。

このフォルダはツール更新時にも削除しないでください。