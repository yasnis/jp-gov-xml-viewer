# 電子公文書ビューワー | jp-gov-xml-viewer

公的機関が発行する電子公文書（XML形式）をブラウザ上でプレビューし、PDFとして保存するツールです。
すべての処理はブラウザ内で完結するため、外部サーバーへのアップロードは発生しません。

[👉 **電子公文書ビューワーを開く (GitHub Pages)**](https://yasnis.github.io/jp-gov-xml-viewer/)

---
### 使い方
1.  [ツールのページ](https://yasnis.github.io/jp-gov-xml-viewer/)を開きます。
2.  公文書データが入った **ZIPファイル** を画面の枠内にドラッグ＆ドロップします。
3.  プレビューが表示されたら、右上の **「PDFとして保存（印刷）」** ボタンを押します。
4.  印刷画面で「PDFに保存」を選択して保存してください。

---

### 技術スタック
*   **Frontend**: HTML5, CSS3, Vanilla JavaScript
*   **Libraries**: [JSZip](https://stuk.github.io/jszip/) (v3.10.1) - Client-side ZIP extraction
*   **Core Logic**: `DOMParser`, `XSLTProcessor`

### アーキテクチャ
*   Serverless / Static HTML architecture.
*   ZIP内のXMLを走査し、`<?xml-stylesheet?>` または同階層の `.xsl` を解決して変換します。
*   印刷用CSS (`@media print`) により、A4サイズへの最適化と改ページ制御 (`page-break-after`) を行っています。

### 免責事項
本ツールは、公的機関が発行する電子公文書をブラウザ上でプレビューし、PDFとして保存するための補助的なツールです。本ツールによって生成されたPDFの正確性、完全性、または法的有効性を保証するものではありません。公的機関が提供する公式な電子公文書またはその表示方法を代替するものではありません。本ツールの使用により生じたいかなる損害についても、開発者は責任を負いません。