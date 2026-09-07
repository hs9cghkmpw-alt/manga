# ネガティブプロンプト集 / Negative Prompts

全ページ共通で使用するネガティブプロンプト。`scripts/image_prompts.md` /
`scripts/image_prompts_en.md` の各ページプロンプトと必ずセットで使用する。

## 日本語

```
文字化けした文字、意味不明な漢字、崩れた日本語、判読不能なテキスト、
画像内に直接描き込まれた日本語吹き出し文字、
丸い人物アイコンだけの構図、顔だけのアップ+巨大テキストボックス、
PowerPointスライド風レイアウト、パンフレット風レイアウト、年表だけの構成、
1ページに人物の顔1つだけ＋残りが文章、背景のない人物単体、
同一構図の使い回し、元画像の単純な引き伸ばし・分割、
過度にホラー的な仮面オブジェクト、実在の仮面（お面）そのもの、
常時介助が必要な様子（車椅子・点滴・寝たきり等の過剰な医療的表現）、
暴力描写の直接的・グラフィックな表現、低品質、崩れた手、崩れた顔、
過剰なデフォルメ、ギャグ漫画的な誇張表現、白目・アヘ顔等の過度な表情誇張、
ウォーターマーク、署名、フレーム外のノイズ、極端な低解像度、ブレ、
医療資料的な無機質デザイン、モノクロ（フルカラー作品のため）、
背景に無意味な英数字の羅列やロゴのような模様。
```

## English

```
garbled or corrupted text, nonsensical kanji, broken/malformed Japanese characters,
illegible text, Japanese speech-bubble lettering rendered directly in the image,
circular icon-only character portraits, close-up face with a giant text box,
PowerPoint-slide layout, brochure/pamphlet layout, plain timeline-only layout,
a single close-up face with the rest of the page as text, floating character with no background,
repeated/reused identical panel compositions, simple stretching or slicing of a source photo,
an overtly horror-style physical mask object, a literal theatrical/festival mask,
depiction implying need for constant physical care (excessive medical imagery: wheelchair, IV
drip, bedridden state) unless explicitly required by the script,
graphic or explicit depiction of violence, low quality, malformed hands, distorted faces,
excessive chibi/gag-manga exaggeration, exaggerated ahegao/rolled-eyes expressions,
watermark, signature, out-of-frame noise, extreme low resolution, motion blur,
sterile clinical-brochure design, monochrome/grayscale (this is a full-color work),
meaningless alphanumeric strings or logo-like patterns in the background.
```

## 使用上の注意

- ネガティブプロンプトはあくまで補助。最終的な品質保証は `docs/QA_CHECKLIST.md` に基づく
  人手での拡大確認で行う。
- 「暴力描写」「常時介助」に関する項目は、`CLAUDE.md` の禁止事項（DV描写を直接的に描かない、
  常時介助が必要な人物として描かない）を画像生成の段階でも徹底するためのもの。
- 日本語文字が生成されてしまった場合は、そのコマを再生成するか、文字部分のみを塗り消してから
  正規フォントで組版し直す。
