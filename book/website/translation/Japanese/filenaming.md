(pd-filenaming)=
# ファイル、フォルダ、その他の項目に名前を付けています

## 前提条件 / 推奨スキルレベル

なし

## Summary

ファイル、フォルダ、およびその他の研究コンポーネントに一貫して明確に名前を付けることで、あなたの仕事を見つけられるようにすることができます。 自分自身や共同研究者や研究に関心を持つ人々に理解され再利用されます これは、他の人がデジタルオブジェクトが何であるかを理解することを可能にします: ファイルに含まれているものとそれらをどこに見つけるか。 さらに、ファイル名の簡単なヒントに従うことで、コンピュータが識別して処理できるようにすることができます。

## これがあなたを助ける方法/これが有用である理由

良い名前を使用することは、おそらくあなたの研究プロジェクトの再現性と再利用性を向上させる最も簡単な方法です。

## 章の内容

命名には3つの原則があります。 最初の2つはあらゆる種類のものに適用され、3つ目はファイル {cite:ps}`Bryan2015Filenaming` を追跡するためのオプションです。

ファイル名は次のようにします:
1. 読み込み可能なマシン
2. 人間が読めます
3. オプション: 既定の順序でうまくプレイ


それらの意味について詳しく説明する前に、悪いファイル名と良いファイル名の例をいくつか見てみましょう。

| ❌不正です                                             | ✔️良い                                             |
| ------------------------------------------------- | ------------------------------------------------ |
| `Myabstract.docx`                                 | `2020-06-08_abstract-for-sla.docx`               |
| `Joeのファイル名 スペースとPunctuation.xlsxを使用`              | `Joes-filenames-are-getting-better.xlsx`         |
| `図1.png`                                          | `Fig01_scatterplot-talk-length-vs-interest.png`  |
| `fig 2.png`                                       | `Fig02_histogram-talk-attendance.png`            |
| `JW7d^(2sl@deletethisandyourcareerisoverWx2*.txt` | `1986-01-28_raw-data-from-challener-o-rings.txt` |


### 読み込み可能なマシン

デジタルコンポーネントの名前は、コンピュータではわかりやすいはずです。 コンピュータは名前のようにスペースを持たず、意図的に区切り文字を使用し、特殊文字やアクセント文字を使用しません。 コンピュータは大文字と小文字を区別しますので、 `cat.txt` と `Cat.txt` は異なるファイルです。

The file names `Joe´s Filenames Use Spaces and Punctuation.xlsx` and `JW7d^(2sl@deletethisandyourcareerisoverWx2*.txt` shown above use empty spaces and special characters (`´`, `^`, `(`, `@`,`*`), which can lead to difficulties, for example when you want to send it someone else's computer.

良いファイル/フォルダ名は検索が簡単で(正規表現を使用しても)、計算が簡単です (例えば、 `_` または `-` 文字で分割するなど)。

### 人間が読めます

人間の可読性を達成するため 短い(< 25 文字)でも、ファイル/フォルダの内容に関する情報を含む説明的な名前を持つことが役に立ちます。 ファイル名の単語境界は、例えば「FileName」や「file_name」などのように、ラクダケースと呼ばれる内大文字化を使用することで示すことができます。 ファイル名にスペースや特殊文字を含めることはできません。

ウェブリンクまたはUniform Resource Locator (URL) の場合、この概念は [clean URL](https://en.wikipedia.org/wiki/Clean_URL) と呼ばれます。

### 既定の順序でうまくプレイ

名前の先頭に番号や日付を追加する良いデフォルトの順序を作成するには、しばしば良いアイデアです。 これにより、ファイルのバージョンまたは時系列に基づいてファイルを昇順にソートします。 たとえば、同じフォルダに異なる日付に作成されたすべてのスライドデッキを整理することがよくあります。 作成日でソートするには、ファイル名を `年月日` で始めることができます(例: `2020-02-21`)。 日付には [ISO 8601規格:YYYY-MM-DD](https://en.wikipedia.org/wiki/ISO_8601) のようなものを使用することをお勧めします。 If you use other numbers, we recommend left padding them with zeros, because your computer will order `003 < 004 < 020 < 100` as opposed to `100 < 20 < 3 < 4`.

論理番号に基づいてフォルダに名前を付けると、将来的に順序が変わると混乱する可能性があります。 例えば、本のチャプター `1_introduction`、 `02_naming_files`、および `03_naming_folders` のあるフォルダがあります。 著者は、本の序文を書き、導入章の前にそれを絞ることを決定します。 これは、彼らが意図した順序を維持するためにすべてのファイルの名前を変更する必要があることを意味します。 これは多く起こり、明らかに、これは逆さまより多くの欠点を持っている。

## Checklist

ここでは、人間と機械で読める {cite:ps}の両方である研究プロジェクト内のファイルを命名するためのいくつかのヒントを紹介します。`Cowles2019Filenaming、Hodge2015Filenaming`:

- ファイルに一貫して名前を付けてください
- 短いが説明的なままにする
- 特殊文字や空白を避けてマシン互換性を保ちます。
- 人間が読めるようにするには、大文字またはアンダースコアを使用してください
- ISO 8601などの日付書式設定を使用します。 `YYYY-MM-DD` でデフォルトの順序を維持できます。
- 該当する場合はバージョン番号を含める
- コラボレーターと作業する際の命名規則を共有/確立する
- データ管理プランで命名規則を記録する


## 次に学ぶべきこと

研究プロジェクトのすべてのファイルを含むフォルダを作成しますか？
{ref}`research compendia<rr-compendia>` の章をご覧ください。