<p align="center"><img src="https://raw.githubusercontent.com/go-compressions/brand/main/social/go-compressions.png" alt="go-compressions/go-compressions.github.io" width="720"></p>

# go-compressions.github.io

Sources for **go-compressions.github.io** — the go-compressions landing page.
Built by [Hugo](https://gohugo.io) — same toolchain and same template
shape as [cloud-boot.github.io](https://github.com/cloud-boot/cloud-boot.github.io)
and [openweft.github.io](https://github.com/openweft/openweft.github.io).
Teal/cyan accent with codec-vs-hash colour coding, plus a three-state
light/dark/system theme toggle (default = system).

## Layout

```text
.
├── hugo.toml                       Site config + per-repo card params ([[params.repos]])
├── content/
│   └── _index.md                   Homepage marker (empty)
├── layouts/
│   └── index.html                  Self-contained homepage (inline CSS/JS, repo cards, theme toggle)
├── static/
│   ├── favicon.svg                 Tab icon
│   └── img/logo.svg                88px org logo
└── public/                         Hugo build output (gitignored — built by CI)
```

Each repository card is a `[[params.repos]]` entry in `hugo.toml`
(`name`, `accel`, `kind`, `type`, `arch`, `result`); `layouts/index.html`
ranges over them. Add or edit a card there, not in the template.

## Build locally

```sh
hugo server -D                            # live reload at http://localhost:1313/
hugo --gc --minify                        # production build → ./public/
```

## Deploy

`.github/workflows/hugo.yml` builds + deploys on every push to `main`.
Configure GitHub Pages on the repo with **Source = "GitHub Actions"**
(not "Deploy from a branch").

## Sibling pages

- [cloud-boot](https://cloud-boot.github.io) — the UEFI bootloader and
  UKI toolchain that ships `lzfse` as its body compressor.
- [go-virtio](https://go-virtio.github.io) — pure-Go virtio drivers.
- [openweft](https://openweft.github.io) — the cloud platform on top.
