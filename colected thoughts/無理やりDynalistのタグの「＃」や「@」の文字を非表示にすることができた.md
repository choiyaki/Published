- RoamResearchの有料プランがちょっと高すぎたので、Dynalistではダメか試してみると、ぼくの使い方ならRoamResearchの機能でなくても、Dynalistの機能で大丈夫なことに気づく。
- [[リンクをクリックするとBacklinkが表示される（そのリンクが記述されている他のトピックが表示される）のを、Dynalistではタグで代用]]できるから。
	- で、これをする際、「#」と言う表記を消したい。
		- ScrapboxやRoamResearchでは、カーソルがその行になければ非表示になる。
			- この機能を実装したい。DynalistのProでの、CSSカスタマイズにて。
				- できた！以下、やり方。
- タグと認識されているclassを特定して、
	- ``t.node-tag.js-prevent-default``
	- それを``display:inline block``にして、
	- ``first-letter``で最初の文字のスタイルをいじって
		- ``color:white``、テキストサイズ1pxに。
	- ただし、「＃」はfirst-letterの対象にならず、スルーされて次の文字が1文字目と認識されるので、「＃」や「＠」の次に「-」を入れて、それを1文字目と認識させて実装できた。
	- なので、タグを付け加えるときは「＃-」や「＠-」と入力してから、タグ名を記述することになる。
- ![](https://gyazo.com/4cc38832c3c6244eb5bb599282fca5fa.img)

#Dynalist 