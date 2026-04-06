---
created: 1743233682
updated: 1775481598
---

![](https://gyazo.com/762596d99ad9cfaa53af28f944053c71/raw)

code:script.js
- 
- import "/api/code/scrasobox/見える文字数カウンター/script.js";
- import "/api/code/choiyaki/行選択⇄ブロック選択をするpopupmenu/script.js";
- //import "/api/code/choiyaki/デイリーページに、特定のページへのリンクを持つページ一覧を表示し、さらに内容を開閉できるようにする/script.js";
- import "/api/code/choiyaki/popupmenuのSplit into new pageをカスタマイズ/script.js";
- import "/api/code/choiyaki/iPhoneアプリのporterでヘッダーを上部に固定する/script.js";
- import "/api/code/choiyaki/iPhoneでinfoboxを表示するuserscript/script.js";
- 
- //enterキーで参加ページを作成する
- $('body').on('keydown',function(e){ // Enterキーで新規ページ作成
      - if(e.target.tagName != "TEXTAREA" && e.target.tagName != "INPUT"){
            - if(e.key == 'Enter'){
                  - var project = location.href.split('/')[[3]];
                  - location.href = `/${project}/new`;
            - }
      - }
- });
- 


code:style.css
-
