# クイックスタート

## 初回使用時の推奨事項

InertiaBonesを初めて使用する場合は、以下のいずれかを推奨します：

- 使用前にアバターを**複製**しておく。
- または、ツールUIの適用時に「**Create Upload Copy**」オプションを有効にする。

これは、新しい自動化ツールを既存のアバター設定に導入する際の優れたワークフロー慣行です。

InertiaBonesは安定性とクラッシュ耐性を考慮して設計されていますが、初回使用時にバックアップを作成しておくことで、懸念なく挙動を確認し、自由に実験することができます。

ワークフローに慣れた後は、通常この予防措置は不要になります。

---

<iframe width="100%" height="500" src="https://www.youtube.com/embed/ysLpTjRzJb8?si=pwyRCc--5lvRZMwd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 基本セットアップ

1. Unityのアバタープロジェクトを開きます。
2. Toolsメニューから「InertiaBones」を開きます。
3. 変換したいアバターを「**Avatar Root**」にドラッグします。
4. 変換したいボーンを「**Source Bone**」リストにドラッグします（例：太もも、胸など）。
5. 内蔵プリセットを選択するか、独自の設定を作成します。
6. 「**Apply**」をクリックし、プレイモードで結果を確認します。
7. 納得がいくまで上記の手順を繰り返します。
8. 満足したら、「**Scan & Fill**」を使用してすべてのコントローラーを対象にし、「**Bake converted meshes as assets**」をオンにします。
9. 「**Apply**」をクリックして、メッシュをアセットとしてベイクします。これにより、プレハブとして安全になり、プロジェクトの再起動後も状態が維持されます。
10. 完了です！

!!! info "情報"
    InertiaBonesは、アップロード前の**最終工程**として使用することを想定しています。メッシュやアーマチュアに変更を加える他のツールを使用する場合は、InertiaBonesを適用する前にそれらのツールを使用してください。

---

## 推奨ワークフロー

**調整中：**
- Sessionモード（セッションモード）を使用
- 自由に反復調整
- アセットを作成せずに設定を微調整

**確定時：**
- Bakeモード（ベイクモード）に切り替え
- 1回「Apply」を実行してベイク
- 古いバージョンはRetention（保持）設定による自動クリーンアップに任せる