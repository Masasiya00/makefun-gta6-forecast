# GTA VI launch-day Twitch audience — research notes

How the forecast model is calibrated. All figures checked live 2026-11-17 (browser.search + SullyGnome + Take-Two filings + Sensor Tower). Where a number is unpublished, that is stated, not guessed.

## 1. The fanbase, consolidated into ONE number

| Signal | Figure | Source |
|---|---|---|
| GTA series copies sold-in | **470M+** (VGChartz 480M at 30 Sep 2026) | Take-Two SEC filings, Aug/Nov 2026 |
| GTA V copies sold-in | **230M+** (~235M, Zelnick, 9 Nov 2026 call) | Take-Two |
| GTA San Andreas / IV / III / Vice City | ~27.5M / ~25M / ~17.5M / ~17.5M | Take-Two / VGChartz |
| GTA V day one | 11.21M copies, $815M in 24h; $1B in 3 days | Take-Two |
| GTA IV day one | 3.6M copies, $310M; 6M first week | Take-Two |
| GTA Online monthly players | **~18.3M MAU** (Ampere via Statista 2025); 15M+ MAU (AFP Nov 2026); ~9.9M WAU, ~4M DAU | Ampere / AFP |
| GTA VI pre-orders (10 Nov 2026) | **$1.1B revenue, 11.3M copies** (~10.3M digital, ~$1B through 11 Nov) | Sensor Tower |
| GTA VI purchase intent | 29% — highest ever recorded (Circana) | Circana |
| GTA V Steam concurrents | ~159,700 avg early 2026; all-time peak 187,059 (4 Mar 2025) | SteamDB |

**Consolidation method:** copies sold-in over-counts fans (one fan owns several
titles: V + SA + IV + Online). Unique owners ≈ 470M+ copies ÷ ~1.9 copies per
fan ≈ **~250M unique GTA owners**. Cross-checks: 18M monthly active GTA Online
players (the engaged core), 11.3M GTA VI pre-orders already (people who paid
before launch), and ~1B+ trailer views (below). The three independent anchors
(owners ~250M, actives ~18M, pre-orders 11.3M) bracket the same story: a
quarter-billion-person franchise, ~18M playing monthly, ~11M already holding
a GTA VI copy.

**ONE fanbase number: ~250 million unique GTA fans** (engaged core ~18M monthly,
11.3M pre-ordered GTA VI).

## 2. GTA VI trailer viewers across ALL social media

| Trailer | Platform | Views |
|---|---|---|
| Trailer 1 (4 Dec 2023) | YouTube | **93M in first 24h** (Guinness: 90,421,491); **~301.8M total** (10 Nov 2026) |
| Trailer 1 | all platforms, 24h | 93M+ (YouTube only; other platforms not published separately) |
| Trailer 2 (6 May 2025) | **All platforms, first 24h** | **475M+** (Rockstar, via THR) |
| Trailer 2 | YouTube, first 24h | ~83.6M; **~187.1M total** (10 Nov 2026) |
| Trailer 2 | TikTok, first 24h | 2M+ views (Rockstar's first TikTok post; 1.1M followers in a day, 380K+ likes) |
| Trailer 2 | X / Instagram / Facebook / others, first 24h | ~389M combined — **per-platform split NOT published** (only the 475M total is official) |
| Extended Look (27 Aug 2026) | YouTube | ~35.1M total (10 Nov 2026) |
| Extended Look | Netflix | 31.1M views 27–30 Aug, #1 in 87/93 countries |
| Launch Trailer (15 Oct 2026) | YouTube | 76.2M total (10 Nov 2026) |
| **Official YouTube total (4 videos)** | | **~600.2M** (10 Nov 2026) |
| GTA 6-related pre-release videos | YouTube (all creators) | 40B+ views globally (YouTube Culture & Trends 2026) |
| Fan hype sample (SonderLabs, Sep–Oct 2026) | 597 fan posts | 80.7M views (YouTube 50.1M, TikTok 24.2M, Instagram 6.4M) |

**Consolidated trailer reach: ~1B+ official views** (YouTube ~600M + Netflix
31M + Trailer 2 non-YouTube ~390M in its first 24h alone). 24h velocity:
Trailer 1 did 93M on YouTube alone in a day; Trailer 2 did 475M+ across
platforms in a day — the fastest trailer launch ever for a game. GTA IV
(2008) trailer, for comparison: no comparable public view count survives
(pre-YouTube-metrics era); it is not used — the GTA VI trailers are the
signal, and they say the launch-day audience will be the biggest in
gaming history.

## 3. Average age of GTA fans

| Source | Average age |
|---|---|
| Sensor Tower, GTA VI players | **34** (typical; 57% under 35, 72% male) |
| Rascasse, GTA Online fans (US) | **26.1** (85.8% male, 61% aged 16–24) |
| Brazil PGB 2026 | ~38 male / ~34.5 female |
| General GTA surveys | 25–30 (55% 18–29, 22% 30–39) |
| Twitch audience overall | ~26 (72% under 34; US 20–29: 35.4%, 30–39: 34.3%) |
| **Consolidated** | **~30–31** (mean of the source estimates) |

**How age feeds the model:** a working-age audience (~30) means viewing
concentrates in the evening, not at the midnight unlock. That is why the
model's curve dips after hour 1 (the UK-midnight rush is mostly the
hardcore + Oceania) and peaks at hours 17–22 UTC — European evening plus
US afternoon — exactly what every practice launch and every big donor
shows. The age estimate is a shape prior, not a scale input: it supports
the donor curve's evening peak rather than a midnight spike.

## 4. Twitch scale anchors

- GTA V category: all-time peak **1,158,046** (2021); RP era avg 186,400,
  peak 312,800, 44.2M watch hours/month; Nov 2026 live ~111,623, highest
  day 330,834 (15 Nov 2026).
- GTA VI category: **1,240 viewers / 181 channels** on the house probe
  (17 Nov); **max 1,418,094 at 2026-08-27T19:00Z** — the Extended Look
  premiere hour. The category has already proven it can hold 1.4M+
  viewers for a single event.
- GTA V on Twitch at the same probe read: 81,611 viewers / 3,514 channels.

## 5. How the research calibrates the model

1. **Scale regime:** 11.3M pre-orders + ~1B trailer views + a 1.4M category
   peak already → the launch-day hour-1 print will be in the big-donor
   regime (hundreds of thousands, likely 250K–1M+). The model therefore
   lives on the size-conditioned (kernel) branch, not the global median:
   for huge hour-1 prints the day peaks at only ~1.0–1.3× hour 1 (big
   donors: ELDEN RING 0.95×, Cyberpunk 1.26×, Diablo IV 1.26×, Hogwarts
   1.30×), while the unconditioned median (2.40× peak) would over-predict
   by more than 2×.
2. **Shape:** the unlock wave (NZ → CET → UK → US East → US West) plus a
   ~30-year-old working audience → dip at hours 2–4, climb from hour 6
   (US East unlock), peak hours 17–22. The donor curves and all four
   practice launches show exactly this; the model learns it from the
   comparables, it is not hand-drawn.
3. **Example forecast** (ratios, not a fixed number — the program forecasts
   from the real hour-1 print at the deadline):
   - hour-1 print 500,000 → median peak ~518,000 (hour 19, 1.04×),
     hour-2 median 0.98×, hour-4 0.72×, hour-12 0.58×, hour-24 0.84×.
   - hour-1 print 250,000 → median peak ~317,000 (1.27×).
   - hour-1 print 1,000,000 → median peak ~1,004,000 (1.00×).
   The 90% band (q05–q95) is roughly ×/÷ 1.8–2.5 around the median at
   peak hours, from the kernel residual spread — honest about how much a
   launch day can surprise.
