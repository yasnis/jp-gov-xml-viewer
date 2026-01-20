# jp-gov-xml-viewer

電子公文書（XML形式）をブラウザ上でプレビューし、PDFとして保存するツールです。
すべての処理はブラウザ内で完結するため、外部サーバーへのアップロードは発生しません。

[👉 **デモを開く (GitHub Pages)**](https://yasnis.github.io/jp-gov-xml-viewer/)

---

## 👩‍💻 利用者の方へ

### 使い方
1.  [ツールのページ](https://yasnis.github.io/jp-gov-xml-viewer/)を開きます。
2.  公文書データが入った **ZIPファイル** を画面の枠内にドラッグ＆ドロップします。
3.  プレビューが表示されたら、右上の **「PDFとして保存（印刷）」** ボタンを押します。
4.  印刷画面で「PDFに保存」を選択して保存してください。

### 特徴
*   **安心のセキュリティ**: ファイルはインターネット上のサーバーに送信されず、あなたのパソコン（ブラウザ）の中だけで処理されます。
*   **一括変換**: ZIP内に複数の文書が含まれている場合、すべてまとめて縦に連結して表示します。

---

## 🛠 エンジニアの方へ

### 技術スタック
*   **Frontend**: HTML5, CSS3, Vanilla JavaScript
*   **Libraries**: [JSZip](https://stuk.github.io/jszip/) (v3.10.1) - Client-side ZIP extraction
*   **Core Logic**: `DOMParser`, `XSLTProcessor`

### アーキテクチャ
*   Serverless / Static HTML architecture.
*   ZIP内のXMLを走査し、`<?xml-stylesheet?>` または同階層の `.xsl` を解決して変換します。
*   印刷用CSS (`@media print`) により、A4サイズへの最適化と改ページ制御 (`page-break-after`) を行っています。

### ローカル開発・実行
特別なビルド手順は不要です。
```bash
git clone https://github.com/yasnis/jp-gov-xml-viewer.git
# index.html をブラウザで開くだけで動作します
```

### デプロイ
GitHub Pages などの静的ホスティングサービスで即座に公開可能です。
