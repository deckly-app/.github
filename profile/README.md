<p align="center">
  <img src="https://raw.githubusercontent.com/deckly-app/Deckly/main/assets/logo/deckly.svg" width="112" alt="Deckly logo">
</p>

<h1 align="center">Deckly</h1>

<p align="center">
  An independent, open-source app for Stream Deck hardware.<br>
  Pure Rust · Windows, Linux and macOS · MIT licensed
</p>

<p align="center">
  <a href="https://github.com/deckly-app/Deckly/releases/latest"><b>Download</b></a> ·
  <a href="https://github.com/deckly-app/Deckly"><b>Source</b></a> ·
  <a href="https://deckly-app.github.io/Deckly/"><b>Plugin SDK docs</b></a> ·
  <a href="https://github.com/deckly-app/Deckly/blob/dev/CHANGELOG.md"><b>Changelog</b></a>
</p>

---

Deckly is an alternative to the official Stream Deck app. It does what you
are used to there: profiles, pages, folders, multi-actions and built-in
actions. What makes it different:

- **Open source.** MIT licensed: read the code, change it, build it yourself.
- **Light.** A native Rust app with no web browser inside, that waits for
  key presses instead of checking for them all the time, so it stays out of
  the way of your games and streams.
- **Linux too.** Windows, macOS and Linux, from one code base.

Moving over is easy: one click brings your setup from the official app.

Plugins made for the Stream Deck SDK run in Deckly too, but not every one
works yet:

- Plugins installed from the official Marketplace are encrypted, so Deckly
  cannot use those copies; get the plugin from its author's own download.
- A plugin built only for Windows runs on Linux and macOS through Wine, as
  best effort; one built only for macOS does not run on Linux.
- Some plugins may still fail. The
  [Plugins section](https://github.com/deckly-app/Deckly#plugins) has the
  details, and [issues](https://github.com/deckly-app/Deckly/issues) about a
  plugin that does not work are welcome.

> Deckly is unofficial and not made, approved, or supported by Elgato or
> Corsair. It is in early alpha: only the Stream Deck MK.2 has been tested on
> real hardware so far.

## Install

| System | How |
| --- | --- |
| **Windows** | Download [deckly-setup-windows-x64.exe](https://github.com/deckly-app/Deckly/releases/latest/download/deckly-setup-windows-x64.exe) and run it. No administrator rights needed. |
| **macOS** | `brew install deckly-app/tap/deckly` |
| **Linux** | `curl -fsSL https://raw.githubusercontent.com/deckly-app/Deckly/main/install.sh \| sh` |

More ways, and the device rules Linux needs, are in the
[Deckly README](https://github.com/deckly-app/Deckly#install).

## Write a plugin in Rust

Deckly has its own plugin system next to the Stream Deck one: a plugin is a
small Rust program, and Deckly draws its keys and its settings forms.

```sh
cargo install deckly-cli
deckly-cli create
cd my-plugin && deckly-cli dev
```

| Crate | What it is |
| --- | --- |
| [`deckly-sdk`](https://crates.io/crates/deckly-sdk) | The library for writing plugins: actions, settings, key faces, a test harness. |
| [`deckly-cli`](https://crates.io/crates/deckly-cli) | The plugin tool: `create`, `dev`, `build`, `validate`, `pack`. |
| [`deckly-plugin-protocol`](https://crates.io/crates/deckly-plugin-protocol) | The messages between Deckly and its plugins, shared by both sides. |

Start with [Getting started](https://deckly-app.github.io/Deckly/getting-started.html).

## Repositories

| Repository | |
| --- | --- |
| [Deckly](https://github.com/deckly-app/Deckly) | The app, the plugin host, the SDK and the plugin tool. |
| [homebrew-tap](https://github.com/deckly-app/homebrew-tap) | The Homebrew formula for macOS. |

Bug reports and ideas are welcome in
[Deckly's issues](https://github.com/deckly-app/Deckly/issues).
