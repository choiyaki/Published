---
created: 1757893628
updated: 1757894283
---

※自分用。

code:style.css
- //フォントのインポート
- @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+JP&display=swap');
- 
- 
- body {
    - --font-text-theme: 'IBM Plex Sans JP', sans-serif;
    - /* 編集ビューのインデント幅 */
    - --list-indent: 1.2em; 
    - /* プレビュー/リーディングビューのインデント幅 */
    - --list-indentation: 1.2em;
- }
- 
- 
- /* リストのバレットとテキストの間隔を広げる */
- .markdown-source-view.mod-cm6 .list-bullet {
    - padding-right: 0.2em; /* プレビューモードでの間隔 */
- }
- 
- .HyperMD-list-line {
    - padding-left: 0.2em; /* ライブプレビューモードでの間隔 */
- }
- 
- /* プレビュー/リーディングビューでの調整 */
- ul, ol {
    - padding-left: 1.8em; /* 必要に応じて調整 */
- }
-
