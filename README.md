# 週刊ENDO通信

AI編集部が毎週まとめる内分泌の最新知見サイト（GitHub Pages）。
公開URL: https://20qolufiofleity14-lab.github.io/end-weekly/

## 構成
- `index.html` … サイト本体。`data/` のJSONを読んで表示する。号ごとのHTMLは作らない。
  - `#` 最新号 / `#issue-YYYY-MM-DD` 各号 / `#archive` バックナンバー / `#classics` 必読ライブラリ（雑誌別）
- `data/issues.json` … 全号の配列。新しい号は配列に追加する（過去号は消さない）。
- `data/classics.json` … 必読クラシックの全件（同じ論文は二度載せない）。

## 号のデータ（issues.json の1要素）
```
{ "id": "YYYY-MM-DD", "issue": "Vol.N", "date": "表示用の日付と対象期間", "top": "記事id",
  "room": [ {"who": "編集長|糖尿病デスク|…|校閲", "cat": "dm", "say": "編集会議での発言"} ],
  "foot": "出典と注意書き",
  "articles": [ {
    "id": "英数字", "cat": "dm|thy|gro|adr|met", "tags": ["誌名","RCT","小児"], "score": 1-5,
    "head": "日本語の見出し", "lead": "ひとこと", "title": "原題",
    "points": [["これまで","…"],["今回","…"],["だから","…"]],
    "oneline": "他の先生に一言で伝えるなら",
    "design": "…", "result": "…", "clinic": "…", "limit": "…", "check": "校閲メモ",
    "journal": "誌名 日付", "pmid": "…", "doi": "…", "url": "PMIDがない記事の出典URL（任意）"
  } ] }
```
カテゴリ: dm 糖尿病・肥満 / thy 甲状腺・骨Ca / gro 成長・思春期 / adr 副腎・性分化 / met 先天代謝

## 必読クラシック（classics.json の1要素）
```
{ "pmid": "…", "doi": "…", "pmc": "PMCxxxx（任意）", "cat": "…", "journal": "NEJM", "year": "1993",
  "title": "原題", "head": "日本語見出し", "why": "なぜ必読", "point": "結論の要点", "now": "今の診療とのつながり",
  "issue": "紹介した号のid" }
```
