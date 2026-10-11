# concier-chan's kit

<img src="assets/concier-chan.png" width="96" align="right" alt="concier-chan">

atsushiootani がつくった、エージェントと毎日一緒に働くための Claude Code プラグイン集。
このリポジトリは Claude Code の**プラグインマーケットプレイス**になっている。
中身は [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) というカタログ 1 枚で、
どのプラグインがあってどこから取ってくるかを Claude Code に教える。プラグイン本体はそれぞれ別のリポジトリにある。

[English README](README.md)

## 入れかた

Claude Code を使っていれば誰でもここから入れられる。アカウント登録や申請は要らない。
最初に一度だけカタログを登録する:

```bash
claude plugin marketplace add atsushiootani/concier-chan-kit
```

あとは `<名前>@atsushiootani` でプラグインを入れる:

```bash
claude plugin install prompt-timeline@atsushiootani
```

Claude Code 2.1.275 以降なら、セッションの中から 1 行で両方済ませてもいい:

```
/plugin install prompt-timeline --marketplace atsushiootani/concier-chan-kit
```

カタログを登録したあとは、セッションで `/plugin` を開けばこのキットの一覧が出る。

## プラグイン

| プラグイン | なにをするか | 呼び出し |
|---|---|---|
| [**Prompt Timeline**](https://github.com/atsushiootani/prompt-timeline) | 自分の Claude Code の 1 日を 1 枚のページにする。API 換算の金額、エージェントの稼働時間、時間帯ごとの形、セッションの順位、その日の瞬間。手元の transcript しか読まない。 | `/prompt-timeline:build` |
| [**ubiqdoc**](https://github.com/atsushiootani/ubiqdoc) | ドキュメントを読みながら、語句をドラッグしたその場で AI に聞けるリーダー。答えはポップオーバー・子セクション・リンクとして文書に書き込まれ、前の返答を待たずに何個でも聞ける。Node 18 以上と、ログイン済みの `claude` CLI が要る。 | `/ubiqdoc:open <file.html>` |

## 更新

プラグインが増えると、このカタログに足されていく。入れたものを新しくするには:

```bash
claude plugin update prompt-timeline@atsushiootani
```

`/plugin` でこのマーケットプレイスの自動更新をオンにしてもいい（Anthropic 以外のマーケットプレイスは
既定でオフ）。ここのプラグインはバージョン番号を持たないので、公開されたコミットがそのまま新しい版になる。

このキットをまるごと外すなら `claude plugin marketplace remove atsushiootani`。

## ライセンス

カタログとこの README は MIT（[`LICENSE`](LICENSE)）。各プラグインのライセンスはそれぞれのリポジトリにある。

`assets/concier-chan.png` は **MIT の対象外**。Google Gemini で生成したもので、
Google の利用規約（生成物の所有権を Google は主張しない）のもとで使っている。
純粋に AI が生成した画像には著作権が認められない可能性があるため
（米国著作権局 *Copyright and Artificial Intelligence, Part 2: Copyrightability*, 2025年1月）、
**著作権は主張しない**。仮に何らかの権利が生じる場合も
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) とする。好きに使ってほしい。
ファイルは生成されたままバイト単位で同梱してあり、Google の不可視ウォーターマーク
SynthID と C2PA の来歴情報が入っている可能性がある。剥がさないでほしい。
