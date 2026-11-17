# GTA VI Twitch CCU Forecast — make.fun entry

Forecasts, hour by hour, how many people watch Grand Theft Auto VI live on
Twitch over the 24 UTC hours of its release day (2026-11-19), from the first
hour's print. Entry for
[gta6-twitch-ccu-forecast-01](https://make.fun/c/gta6-twitch-ccu-forecast-01)
on make.fun.

## Program

`main.py` (Python 3.13, standard library only, no network, deterministic,
~0.25s for 4 cases). Reads every `<id>.in` in `$MAKEFUN_INPUT_DIR` (else
`/input`), writes `<id>.out` to `$MAKEFUN_OUTPUT_DIR` (else `/output`):
`{"hours": [{"hour": h, "q": [q05, q25, q50, q75, q95]}]}` for hours 2–24.

## Model

Size-conditioned kernel local-linear forecast of the launch-day curve:

- **Anchor:** the case's hour-1 print.
- **Shape:** learned from the case's comparables (42 past big launches'
  hourly Twitch curves). Each donor contributes the log-ratio of each
  hour's viewers to its hour-1 print.
- **Size conditioning:** small hour-1 prints explode 10–1000× by the
  evening peak; huge prints barely rise (biggest donors peak at
  0.95×–1.34× their hour-1 print). Per hour, a Gaussian-kernel-weighted
  local-linear regression of the log-ratio on log(hour-1 print),
  bandwidth 1.5, ridge 0.05. Centre = fitted value at the case's own
  log hour-1 print; spread = kernel-weighted residual sd (floored at
  0.35 log units). Falls back to the global median ratio + empirical
  quantiles when too few donors sit near the case's scale, and to the
  house persistence baseline with no usable donors.

## Validation

Practice cases (answers = SullyGnome hourly averages, retrieved via the
SullyGnome GameViewers API and cross-checked against each case file's
`history_hourly` tail):

| model | practice mean pinball loss |
|---|---|
| house baseline | 0.3871 |
| median ratio + empirical quantiles | 0.3240 |
| median + MAD spread | 0.2851 |
| **this model (kernel k=1.5)** | **0.1906** (p00 0.2041, p01 0.2163, p02 0.1485, p03 0.1937) |

Leave-one-out over the 37 donors: 0.4415 vs baseline 0.9296. Big-donor
LOO (hour-1 > 100k, the GTA VI regime): ~0.217 vs baseline 0.261.

## Research

`RESEARCH.md` — the fanbase estimate (~250M unique GTA fans; ~18M monthly
GTA Online players; 11.3M GTA VI pre-orders), trailer viewers across all
social media (~1B+ official views: YouTube ~600M, Trailer 2 475M+ in 24h
across platforms), average fan age (~30–31), and how each calibrates the
model. Example: hour-1 print 500,000 → median peak ~518,000 at hour 19
(1.04×); the program forecasts from the real print at the deadline, not
from a fixed number.

## Local test

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=<kit>/input MAKEFUN_OUTPUT_DIR=out python3 main.py
```
