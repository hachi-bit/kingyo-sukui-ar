# 鉢-bit AR (8th Wall / マーカー + World Tracking)

サーバー不要。このフォルダの中身をそのままGitHub Pagesのリポジトリに配置すれば動きます。

## 中身
```
index.html                          ← ARページ本体(これを開くだけ)
image-targets/
  ├── kingyo-target.json            ← マーカー定義ファイル(index.htmlが参照)
  ├── kingyo-target_luminance.png   ← 検出に実際使われる輝度画像
  ├── kingyo-target_cropped.png     ← 補助ファイル
  ├── kingyo-target_thumbnail.png   ← 補助ファイル
  └── marker-original.png          ← 元のマーカー画像(印刷/表示用)
```

## 使い方
1. このフォルダの中身を丸ごとリポジトリのルート(または任意のサブフォルダ)にコピー
2. `git add . && git commit -m "AR追加" && git push`
3. GitHub Pagesが自動デプロイするのを待つ
4. iPhoneのSafariで公開URLを開く
5. `marker-original.png`(または`kingyo-target_luminance.png`)を画面や紙に表示・印刷して、カメラでスキャン

## 注意点
- `index.html`内の3Dオブジェクトは仮の立方体(BoxGeometry)です。鉢-bitの.glbモデルに差し替える場合は、`initScene()`内のオブジェクト生成部分を`THREE.GLTFLoader`に変更してください。
- サブフォルダに配置する場合、`imageTargets: ['./image-targets/kingyo-target.json']`のパスをフォルダ構成に合わせて調整してください。
- マーカー画像を別のものに差し替えたい場合は、新しい画像を`image-target-cli`で変換し直す必要があります(Claudeに再依頼可能)。
