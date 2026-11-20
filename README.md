# News Image — 19 November 2026 (submit package)

make.fun bounty: **"Sum up 19 November's world news in one image"**
($250 shared prize pool, 50 places). Free entry only, via referral
https://make.fun/r/xdjs4mdb (code `xdjs4mdb`).

**Deadline: Saturday 21 November 2026, 07:00 WIB.**
Status: ready to push — **NOT submitted yet.**

## Contents of this folder (this is the repo root to push)

| File | What it is |
| --- | --- |
| `main.py` | Entry point (Python 3.13, **stdlib only**, no network). Copies bundled `entry.png` to `/output/entry.png`, deterministically. |
| `entry.png` | The entry image — 1024×576 px PNG, 265,918 bytes (< 1 MiB, ≤ 1024×1024). Resized from the 1200×675 original, which exceeded the 1024 px limit. |
| `generate.py` | Renderer that drew the image (Python + Pillow, local only, no network). Kept for transparency; not used by `main.py`. |
| `README.md` | This file. |
| `LICENSE` | MIT (OSI-approved). |
| `TRANSCRIPT.md` | Transcript status — read before submitting. |

The image sums up 19 Nov 2026 in 6 stories (Trump–Xi–Putin Shenzhen
summit, ICJ Myanmar/Rohingya genocide ruling, Anthropic IPO, Gaza /
Hormuz tanker mines, COP31, Voyager 1 one light-day out). Full story
list and sources: see `../README.md` in the parent folder.

## How to run

```bash
python3 main.py            # writes /output/entry.png
```

## How to verify (done locally 20 Nov 2026)

```bash
python3 main.py /tmp/run1/entry.png
python3 main.py /tmp/run2/entry.png
sha256sum /tmp/run1/entry.png /tmp/run2/entry.png   # identical hashes
file entry.png                                        # PNG 1024x576, < 1 MiB
```

Both runs must write byte-identical output. Verified: see hashes in
the verification log below (re-check after any change).

## Verification log (20 Nov 2026, this machine)

- `entry.png`: 1024×576, 265,918 bytes, PNG.
- `main.py` run 1 and run 2: byte-identical, SHA-256
  `ce4f6e1cde47aee538efb39a207a35bf0fa4e7de50d811e28c30765ef1f55167`
  (same as `entry.png` itself, since `main.py` copies it exactly).
  Also verified with no-arg run: writes `/output/entry.png`, same hash.
- `main.py` imports (AST check): only `hashlib`, `pathlib`, `shutil`,
  `sys` — stdlib only, no network.
- Resized image visually inspected: all 6 headlines, summaries,
  sources, header and footer legible; no clipped or overlapping text.

## Still needed to submit (see TRANSCRIPT.md)

1. A public GitHub repo of Cindy's own, created after the competition
   opened, containing exactly this folder's contents at its root.
2. Cindy's make.fun account (she confirmed "sudah masuk" via Google,
   20 Nov ~10:31 WIB — username not verified from here).
3. The agent-session transcript upload required per submit.
4. Solana wallet address for USDC prize payout (Cindy said she will
   send it later).
