# PicoRubyマイコン作品画像フォルダ

このフォルダにはPicoRubyとマイコンを使った習作の画像を配置します。

## 画像仕様

### サイズと縦横比
- **縦横比**: 1:1（正方形）推奨
- **推奨サイズ**: 800×800px ～ 1200×1200px
- **最小サイズ**: 600×600px
- **最大サイズ**: 1500×1500px程度

### フォーマット
- **JPG**: 写真の場合（推奨）
- **PNG**: 透過が必要な場合
- **WebP**: さらに最適化したい場合

### ファイル名の例
```
led-matrix-01.jpg
atom-matrix-wave.jpg
picoruby-2025-01.jpg
```

## 使用方法

`pico/index.html` で以下のように使用します：

```html
<div class="work-card">
    <div class="work-image">
        <img src="../assets/works/pico/led-matrix-01.jpg" alt="LED Matrix作品">
    </div>
</div>
```

## 画像の最適化

### ファイルサイズの目安
- 1枚あたり100KB ～ 300KB程度を推奨
- 最大でも500KB以下に抑えると読み込みが速くなります

### 最適化ツール
- [TinyPNG](https://tinypng.com/) - JPG/PNG圧縮
- [Squoosh](https://squoosh.app/) - 各種フォーマット対応
- ImageMagick (CLI): `magick convert input.jpg -quality 85 -resize 1000x1000 output.jpg`
