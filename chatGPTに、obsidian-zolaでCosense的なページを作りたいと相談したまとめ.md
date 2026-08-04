---
created: 1785887108
updated: 1785887108
---


なるほど、意図が分かりました 👍
では「あなた向けの説明」ではなく、“自分用の設計メモ”として最適化された形でまとめます。
（説明・配慮・誘導は削って、構造と依存関係だけ残します）

⸻

■ システム定義

目的：
Zola上でCosense的リンク構造（backlinks + 2-hop）を静的生成する

制約：
- Zolaは静的（実行時処理なし）
- リンク解析はビルド前に完結させる


⸻

■ パイプライン

content/*.md
   ↓
link parser（Node.js）
   ↓
graph.json（links）
   ↓
Zola（load_data）
   ↓
HTML


⸻

■ データモデル

{
  "PageA": {
    "outgoing": ["PageB", "PageC"],
    "backlinks": ["PageD"],
    "two_hop": ["PageE", "PageF"]
  }
}


⸻

■ グラフ構築ロジック

1. 全ページ走査
2. [[link]] 抽出
3. 有向グラフ G 構築

4. backlinks:
   inverse(G)

5. 2-hop:
   for each node A:
     H1 = neighbors(A)
     H2 = neighbors(H1)
     H2 から A, H1 を除外


⸻

■ 実行タイミング

build前に必ず実行


⸻

■ ビルド定義（Netlify）

[build]
command = "node scripts/generate-links.js && zola build"
publish = "public"


⸻

■ 依存関係

必須：
- Node.js（リンク解析）
- Zola（SSG）

任意：
- CI/CD（Netlify or GitHub Actions）


⸻

■ 状態遷移

編集（Obsidian / iPhone）
   ↓
git push
   ↓
CI起動
   ↓
graph再生成
   ↓
HTML更新


⸻

■ ローカル開発との差分

ローカル：
  graphが古い可能性あり

対策：
  dev前にスクリプト実行


⸻

■ 表示層（Zola）

load_data → graph.json
page.title をキーに参照


⸻

■ 問題領域

1. ページ名正規化（slug vs title）
2. [[link]] パース精度
3. 2-hopノイズ
4. O(n^2) 増加


⸻

■ 拡張ポイント

- 重み付け（共起数）
- タグ連携
- 更新日フィルタ
- グラフ可視化


⸻

■ 本質

Zola単体では「木構造」
→ 前処理で「グラフ構造」を注入している


⸻

■ 最小要件

- generate-links.js
- graph.json 出力
- load_data 呼び出し
- build pipeline への組み込み


⸻

■ 非本質（削除可能）

- UIのCosense再現
- 完全な双方向リンク
- リアルタイム性


⸻

■ 一行要約

静的サイトに対して、事前計算されたリンクグラフを埋め込んでいる