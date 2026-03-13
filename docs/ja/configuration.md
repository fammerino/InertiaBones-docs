# 設定詳細

## UIの説明

![UI Screenshot](assets/UIScreenshot.PNG)

### ヘッダーボタン:
- **Docs**: 現在表示しているドキュメントページを開きます。
- **Options**: グローバル設定が表示されます。

### Avatar Root / Bones セクション
- **Avatar Root**: 操作対象のアバターを配置します。
- **Bones**: 操作を行うソースボーンを追加するリストです。
    - **Category**: インフルエンス（影響度）スライダーの制御に使用されます。命名規則から自動検出されますが、手動選択も可能です。
    - **Add Bone Slot / Remove**: リストの枠を追加・削除します。
    - **Clear Empty Slots**: ソースボーンが未設定の枠を削除します。
- **Bone List Preset**: 一般的なボーン構成を素早く選択できるドロップダウンです。

### Processing (処理設定)
- **Bake converted meshes as assets**: **Session**（セッション）モードと **Persist**（ベイク）モードを切り替えます。
- **Include Inactive Objects**: 非アクティブなメッシュ（非表示の衣装など）も対象にするかどうかを選択します。
- **Match outfit meshes by bone name**: 推奨設定。Modular Avatar等を使用している場合に、衣装側のアーマチュアに余分なコントローラーが作成されるのを防ぎます。

### Weight Mode (ウエイトモード)
- **Replace (標準)**: ソースボーンのすべてのウエイトを **_Jiggle** ボーンに書き換えます。
- **Split**: ウエイトを数値に基づいて分割します。

### Exclude knee area from weight transfer (膝エリアの除外)
- **Exclusion Range**: グラデーションの範囲。
- **Exclusion Intensity**: 除外の強さ。

### Enable experimental features (実験的機能)
- **Vertical Thigh Jiggle**: 太ももに上下方向の動きを追加する新しいリグセットアップを生成します。

### Debug / Maintenance (デバッグ・メンテナンス)
- **Clean Old Baked Meshes**: 使用されていない古いベイク済みメッシュを削除します。
- **Repair Backup References**: バックアップデータの参照を修復します。