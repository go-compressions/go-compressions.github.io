# go-compressions.github.io

Sources for **go-compressions.github.io** — the go-compressions landing page.
Built by [Hugo](https://gohugo.io) — same toolchain and same template
shape as [cloud-boot.github.io](https://github.com/cloud-boot/cloud-boot.github.io)
and [openweft.github.io](https://github.com/openweft/openweft.github.io).
Warm-amber palette so it reads as a sibling project page.

## Layout

```text
.
├── hugo.toml                       Site config + hero params
├── content/
│   └── _index.md                   Homepage marker (empty)
├── data/
│   └── mesh.toml                   Pipeline visualisation: input / transforms / output
├── layouts/
│   ├── _default/baseof.html        Outer HTML shell
│   ├── index.html                  Homepage body (go-compressions specific)
│   └── partials/
│       ├── nav.html                Topnav with brand + menu
│       ├── footer.html             Footer
│       └── mesh.html               Animated SVG (reads data/mesh.toml)
├── static/
│   └── css/main.css                Warm-amber palette + mesh styling
└── public/                         Hugo build output (gitignored — built by CI)
```

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
