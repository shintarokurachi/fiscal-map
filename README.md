# 財政指標マップ（令和６年度）

全国市区町村の主要財政指標をインタラクティブな地図で可視化します。
[RESAS](https://resas.go.jp/)の財政力指数マップを参考に、総務省の公開データを使って個人で再現したものです。

> **出典：** 総務省「地方公共団体の主要財政指標一覧（令和６年度）」
> https://www.soumu.go.jp/iken/shihyo_ichiran.html
> ※ 本サイトは総務省公開データを二次利用して作成した個人プロジェクトです。

## 🗺️ 見られる指標

| 指標 | 概要 |
|------|------|
| **財政力指数** | 高いほど財政が豊か。1.0以上が不交付団体 |
| **経常収支比率** | 低いほど財政に余裕がある |
| **実質公債費比率** | 低いほど借金返済の負担が小さい |
| **将来負担比率** | 低いほど将来の財政負担が小さい |
| **ラスパイレス指数** | 国家公務員との給与水準比較 |

## 🚀 GitHub Pages で公開する手順

### ステップ1：このリポジトリをGitHubにアップロード

1. GitHubで新しいリポジトリを作成（例：`fiscal-map`）
2. `index.html` と `README.md` をアップロード

### ステップ2：地図データ（GeoJSON）を追加する

`index.html` は地図の境界線データ（GeoJSON）を自動で読み込みますが、
外部からの読み込みが不安定な場合は、以下の手順でリポジトリに含めることを推奨します。

1. 以下のURLから `municipalities.geojson` をダウンロード
   👉 https://github.com/smartnews-smri/japan-topography/raw/main/data/municipality/geojson/s0010/N03-21_210101.json
   （ダウンロード後、ファイル名を `municipalities.geojson` に変更してください）

2. ダウンロードしたファイルを `index.html` と同じフォルダに置く

3. リポジトリにアップロード

### ステップ3：GitHub Pages を有効化

1. リポジトリの **Settings** タブを開く
2. 左メニューの **Pages** をクリック
3. **Source** を `main` ブランチ、`/ (root)` に設定して **Save**
4. 数分後、表示されたURLにアクセスすれば公開完了！

## 📂 ファイル構成

```
/
├── index.html              # メインの地図ページ（財政データ内蔵）
├── municipalities.geojson  # 市区町村の地図境界データ（別途ダウンロード）
└── README.md               # このファイル
```

## 📊 データソース

- **財政データ**：総務省「地方公共団体の主要財政指標一覧（令和６年度）」
  https://www.soumu.go.jp/iken/shihyo_ichiran.html

- **地図データ（GeoJSON）**：smartnews-smri/japan-topography（国土数値情報由来）
  https://github.com/smartnews-smri/japan-topography

## 💻 ローカルで試す方法

HTMLファイルをダブルクリックで開くと、ブラウザのセキュリティ制限でGeoJSONが読み込めない場合があります。
その場合は、以下のいずれかの方法でローカルサーバーを起動してください：

**VS Code をお使いの場合：**
「Live Server」拡張機能をインストールして、`index.html` を右クリック →「Open with Live Server」

**Python がある場合（ターミナルで）：**
```bash
python3 -m http.server 8000
```
その後、ブラウザで `http://localhost:8000` を開く

## ⚖️ ライセンス

財政データは総務省の公開データ（二次利用可）を使用しています。
