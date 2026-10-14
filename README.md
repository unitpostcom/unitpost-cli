# Unitpost CLI

The official command-line interface for [Unitpost](https://www.unitpost.com). Send email and SMS, and manage contacts, domains, templates, campaigns and webhooks from your terminal, your scripts and your CI.

This repository holds the CLI's **releases**: standalone binaries for macOS, Linux and Windows, with checksums. The CLI is also on npm as [`unitpost-cli`](https://www.npmjs.com/package/unitpost-cli).

## Install

```bash
# macOS or Linux, with Homebrew
brew install unitpostcom/tap/unitpost

# macOS or Linux, without Homebrew
curl -fsSL https://www.unitpost.com/install.sh | sh

# Windows (PowerShell)
irm https://www.unitpost.com/install.ps1 | iex

# Anywhere with Node.js 20+
npm install -g unitpost-cli
```

The binaries don't need Node.js. Each [release](https://github.com/unitpostcom/unitpost-cli/releases) has archives for `darwin-arm64`, `darwin-x64`, `linux-x64`, `linux-arm64` and `win-x64`, plus a `SHA256SUMS` file. The install scripts check the download against it and install nothing if it doesn't match.

## Get started

```bash
unitpost login
unitpost email send --from you@yourdomain.com --to someone@example.com \
  --subject "Hello" --text "Sent from the Unitpost CLI"
```

`unitpost login` signs you in with your browser. In CI, set `UNITPOST_API_KEY` instead. Every API operation is a command: `unitpost --help` lists them, and `unitpost <command> --help` shows its flags.

## Upgrade

| Installed with | Upgrade with |
| --- | --- |
| Homebrew | `brew upgrade unitpost` |
| Install script | Run the same install command again |
| npm | `npm install -g unitpost-cli` |

The CLI tells you when a new version is out, with the right command for how you installed it.

## Verify a download yourself

Download the archive and `SHA256SUMS` from the same release, then:

```bash
shasum -a 256 -c SHA256SUMS --ignore-missing
```

## Help

- Docs: https://www.unitpost.com/docs/cli
- Account or sending problems: https://www.unitpost.com/support
- Bugs in the CLI itself: [open an issue](https://github.com/unitpostcom/unitpost-cli/issues)

## License

[MIT](LICENSE)
