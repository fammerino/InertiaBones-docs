# Quick Start

## 初めて使用する場合

初めて InertiaBones を使用する場合は、次のいずれかを推奨します：

- アバターを複製してから使用する  
または
- ツール UI の **Create Upload Copy** を有効にする

新しいツールを既存のアバターに導入する場合、バックアップを作成しておくと安心して試すことができます。

ワークフローに慣れてしまえば、この手順は通常不要になります。

---

## Video Walkthrough

<iframe width="100%" height="500" src="https://www.youtube.com/embed/ysLpTjRzJb8?si=pwyRCc--5lvRZMwd" title="YouTube video player" frameborder="0" allowfullscreen></iframe>

---

## Basic Setup

1. Unity のアバタープロジェクトを開きます  
2. Tools メニューから InertiaBones を開きます  
3. アバターを **Avatar Root** にドラッグします  
4. 揺れを追加したいボーンを **Source Bone** にドラッグします  
5. プリセットを選択します  
6. **Apply** をクリックし、Play Mode で動作を確認します  
7. 設定を調整しながら満足するまで繰り返します  
8. 設定が完成したら **Scan & Fill** を実行し、**Bake converted meshes as assets** を有効にします  
9. **Apply** をクリックしてメッシュをアセットとして保存します  

これで完了です。

---

!!! info
    InertiaBones は **アバターアップロード前の最終工程** として使用することを想定しています。  
    メッシュやアーマチュアを変更するツールは、InertiaBones を適用する前に使用してください。

---

## Recommended Workflow

**調整中**

- Session モードを使用
- 自由に設定を変更
- アセットは作成しない

**設定完成後**

- Bake モードに切り替え
- 一度だけ Apply を実行
- 古いメッシュは自動クリーンアップに任せる

---

## Important Early Notes

!!! warning
    Persist モードでは新しいメッシュアセットが作成されます。  
    既存のメッシュアセットは上書きされません。

!!! info
    Bake モードで既存コントローラーを外すと、ウェイト影響が残っている場合に警告が表示されます。