---
created: 1782473939
updated: 1782488125
---
- obsidianのself-hosted livesyncという同期のためのプラグインを使ってみたところからcouchdbという方式を知り、それをoracle cloudにて運用する環境を構築できた。
- そっから、複数デバイスでメモを同期するのにoracle cloud×couchdbを使うようになり、しばらくobsidianでもlivesyncで使用。
- が、obsidianはmdファイルにして使うが、直接couchdbを読み書きできたらいいんじゃない？という発想でclaude codeでノートアプリ（ios）作成。obsidian使わんくなった。
- 今は完全にoracle cloud×couchdbを中心にしてて、そこのデータを読み書きするタスク管理アプリや、テンプレートに従って直接書き込むことでログを残すアプリ、couchdb上のmd記法と独自記法からスライド表示するアプリなど作成。
- 以下、作成したアプリ。
	- [[couchNotes]]
		- ノートアプリ
	- [[couchTask]]
		- タスク管理アプリ
	- [[couchAI]]
		- AIチャットアプリ
	- [[couchLog]]
		- テンプレートアプリ
	- [[couchSlide]]
		- スライド表示アプリ