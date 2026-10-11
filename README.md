# concier-chan's kit

<img src="assets/concier-chan.png" width="96" align="right" alt="concier-chan">

Claude Code plugins by atsushiootani, for working with agents day to day.
This repository is a Claude Code **plugin marketplace**: one catalog file,
[`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json), that tells Claude Code
which plugins exist and where to fetch them. Each plugin lives in its own repository.

[日本語版 README](README.ja.md)

## Install

Anyone with Claude Code can install from here — no account, sign-up or approval beyond
Claude Code itself. Add the catalog once:

```bash
claude plugin marketplace add atsushiootani/concier-chan-kit
```

Then install any plugin by `<name>@atsushiootani`:

```bash
claude plugin install prompt-timeline@atsushiootani
```

Or do both in one go from inside a session (Claude Code 2.1.275 or later):

```
/plugin install prompt-timeline --marketplace atsushiootani/concier-chan-kit
```

`/plugin` in a session lists everything in the kit once the catalog is added.

## Plugins

| Plugin | What it does | Run |
|---|---|---|
| [**Prompt Timeline**](https://github.com/atsushiootani/prompt-timeline) | A one-page view of a day of your own Claude Code work: API-equivalent spend, agent busy time, the hour-by-hour shape, sessions ranked, and the day's moments. Reads only the transcripts on your machine. | `/prompt-timeline:build` |
| [**ubiqdoc**](https://github.com/atsushiootani/ubiqdoc) | A local document reader: drag any phrase and ask the AI on the spot. Answers are written back into the document as popovers, child sections or links, and several questions can run in parallel. Needs Node 18+ and a logged-in `claude` CLI. | `/ubiqdoc:open <file.html>` |

## Updates

New plugins appear here as they are added to the catalog. To pick up new versions of what you
installed:

```bash
claude plugin update prompt-timeline@atsushiootani
```

or turn on auto-update for this marketplace in `/plugin` (it is off by default for marketplaces
other than Anthropic's). Plugins here carry no version number, so every published commit is a
new version.

To remove everything from this kit: `claude plugin marketplace remove atsushiootani`.

## License

The catalog and this README are MIT — see [`LICENSE`](LICENSE). Each plugin carries its own
license in its own repository.

`assets/concier-chan.png` is **not** covered by that MIT grant. It was generated with Google
Gemini and is used under Google's Terms of Service, which disclaim Google's ownership of
generated output. Because a purely AI-generated image may not be eligible for copyright
protection (see the U.S. Copyright Office, *Copyright and Artificial Intelligence, Part 2:
Copyrightability*, January 2025), no copyright is asserted in it. To the extent any rights do
exist, it is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) —
take it and use it. The file ships byte-for-byte as generated and may carry Google's invisible
SynthID watermark and C2PA content credentials. Please don't strip them.
