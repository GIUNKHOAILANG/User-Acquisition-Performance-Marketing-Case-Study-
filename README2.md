# Cube Escape Collection - User Acquisition Case Study

## Performance marketing analysis for a niche puzzle/escape-room mobile game across three region tiers

---

## Phase 1 - Game analysis: Cube Escape Collection

### Product characteristics

| Dimension | Detail | UA implication |
|---|---|---|
| **Developer** | Rusty Lake (Dutch indie studio, est. 2015) | Small studio = limited creative production budget; every asset must work harder |
| **Genre** | Puzzle / Escape room / Point-and-click adventure | Niche within casual puzzle - smaller addressable audience but higher engagement and retention |
| **Content** | 9 chapters (Seasons, The Lake, Arles, Harvey's Box, Case 23, The Mill, Birthday, Theatre, The Cave) | Sequential content = natural progression hooks for retention; chapter completion events are ideal UA optimisation targets |
| **Art style** | Surrealist, Twin Peaks-inspired, hand-drawn | Highly distinctive visual identity - creatives should lean into the surreal aesthetic, not generic puzzle imagery |
| **Avg session** | 12–18 minutes | Very long for mobile - users who install are engaged; the challenge: get them past the first 3 minutes |
| **Engine** | Unity | Native Unity Ads and ironSource SDK integration; LevelPlay mediation is the natural monetisation stack |
| **Platforms** | iOS, Android, Steam, Web | Mobile is the UA target; Steam is the long-tail organic discovery channel |
| **Downloads** | 5M+ (Google Play, as of 2025) | Mature title with established organic baseline - paid UA is incremental |
| **Rating** | 4.6★ (Google Play), 4.7★ (App Store) | Strong ratings = high ASO conversion potential; should be leveraged in ad copy |
| **Price** | Free (with IAP + ads) | Hybrid monetisation: rewarded ads (primary revenue) + IAP hint packs (secondary) |

### Lifecycle stage assessment

Cube Escape Collection is a **mature catalogue title** (released October 2020, 5M+ downloads). This fundamentally shapes the UA strategy:

- **Organic installs are declining.** The initial launch spike and content updates (latest: v1.4.1, September 2025) have been exhausted. Paid UA is now required to maintain install velocity.
- **The audience is niche but loyal.** Puzzle/escape-room players have higher D1 retention (35–42%) than hyper-casual (25–30%) but the addressable audience is smaller. Broad targeting will waste spend on users who churn in 30 seconds.
- **Content is finite.** Unlike a live-service game with weekly events, Cube Escape has 9 fixed chapters. Once a user completes all 9, the monetisation window closes. This means LTV has a ceiling which the UA strategy must account for.
- **Cross-promotion opportunity.** Rusty Lake has 10+ titles in the same universe (Rusty Lake Hotel, Roots, Paradox, The Past Within). Users acquired into Cube Escape Collection who complete it become warm leads for premium titles. This cross-title LTV is not captured in standard D7/D30 ROAS but is commercially significant.

### Monetisation model deep-dive

| Revenue stream | Share of revenue | Mechanic | Optimisation lever |
|---|---|---|---|
| Rewarded video ads | ~72% (T1), ~85% (T2), ~92% (T3) | Watch ad to receive a hint or unlock bonus content | Increase ad placements per session from 1 to 2–3 without harming retention; test interstitial at chapter completion |
| IAP hint packs | ~28% (T1), ~15% (T2), ~8% (T3) | Purchase hint credits (£1.99, £4.99, £9.99 bundles) | Current IAP rate = 1.4% vs 1.83% benchmark (Unity 2024); price anchoring and first-purchase discount are untested |
| Cross-title upsell | Not directly measured | In-app links to Rusty Lake premium titles (£2.99–£4.99) | Track as a soft metric; attribute to UA cohorts via deep-linking |

---

## Phase 2 - Market research and industry benchmarks

### Sources used

| Source | Data type | URL |
|---|---|---|
| **Admiral Media** - Mobile Game Marketing Benchmarks 2025 | CPI, retention, ROAS, IPM by genre and channel | admiral.media/mobile-game-marketing-benchmarks |
| **Segwise** - CPI, IPM, ROAS Benchmarks 2025 | Regional CPI ranges, network-specific benchmarks | segwise.ai/blog/cpi-ipm-roas-benchmarks |
| **Segwise** - ROAS by Country and Ad Network | T1/T2/T3 ROAS ranges, LATAM churn data | segwise.ai/blog/benchmark-roas-mobile-games |
| **GameBiz Consulting** - UA Trends 2026 | Channel shifts, creative trends, Chinese publisher impact | gamebizconsulting.com/blog/mobile-game-user-acquisition-stats-trends-2026 |
| **Amps33** - Mobile Game Unit Economics 2026 | CPI/LTV by genre, seasonality, Q1–Q4 patterns | amps33.com/insights/mobile-game-unit-economics-2026 |
| **Unity** - UA & Monetisation Trends 2024 | IPM benchmarks, IAP conversion, rewarded ad engagement | gamedevreports.substack.com (Unity data) |
| **Liftoff** - 2025 Mobile Gaming Report | D7 ROAS benchmarks: casual = 7.6–7.8% | Liftoff 2025 annual report |
| **data.ai** (formerly App Annie) | Download estimates, category rankings, competitor traffic | data.ai |
| **Sensor Tower** | Market intelligence, ad creative analysis, keyword rankings | sensortower.com |
| **Mobile Action** | ASO keyword tracking, App Store/Google Play optimisation | mobileaction.co |

### Key benchmarks grounding this analysis

The `ref_benchmarks.csv` file contains 15 benchmarks with sources. The critical ones for decision-making:

**CPI by tier:** T1 puzzle benchmark is $2.10–$4.50 (Admiral Media 2025). Our T1 average is £2.85 - mid-range, suggesting creative optimisation can push this lower. T3 at £0.18 is efficient on installs but the D7 revenue per user is so low (£0.02–0.04) that even cheap installs may not reach break-even.

**D7 ROAS:** The casual puzzle benchmark is 7.6–7.8% (Liftoff 2025). Our blended D7 ROAS is 10.0% - above benchmark, but this is skewed by T1 performance. T3 D7 ROAS is only 3.2%, below the threshold where scaling makes sense without ad monetisation improvements.

**Creative performance:** Unity's 2024 data shows puzzle IPM benchmark at 10.3. Our Playable creative achieves 14.8 IPM - well above benchmark, confirming the format works for this game. Our Static End Card is at 6.5 IPM - 37% below benchmark, flagging creative fatigue or format mismatch.

**Seasonality:** Q1 is the cheapest quarter for mobile UA (Amps33 2026: CPI 15–20% below annual average). This is the scaling window - maximise install volume now before Q3 auction pressure.

---

## Phase 3 - Q1 2026 campaign performance analysis

### Dataset overview

| File | Rows | Grain | Description |
|---|---|---|---|
| `fact_ua_daily.csv` | 36,839 | Day × network × country × creative × platform | Full campaign performance with spend, installs, retention, revenue |
| `fact_aso_weekly.csv` | 130 | Week × keyword × store | App Store Optimisation keyword tracking |
| `summary_creative.csv` | 4 | Creative format | Aggregated creative performance |
| `ref_benchmarks.csv` | 15 | - | Industry benchmarks with sources and implications |

### Headline findings

**1. The Playable creative outperforms everything - but is underweighted in spend.**

| Creative | IPM | CPI (T1) | CVR | D7 ROAS | % of spend |
|---|---|---|---|---|---|
| Playable - Chapter 1 Demo | 14.8 | £2.12 | 18.4% | 14.2% | 22% |
| Video 15s - Puzzle Teaser | 12.1 | £2.65 | 14.8% | 10.8% | 28% |
| Video 30s - Story Atmosphere | 10.2 | £3.10 | 12.1% | 8.4% | 32% |
| Static End Card - Mystery Art | 6.5 | £4.20 | 7.2% | 4.1% | 18% |

The Playable has the highest IPM (14.8 vs 10.3 benchmark), lowest CPI, highest CVR, and highest ROAS - yet receives only 22% of spend. The Static End Card receives 18% of spend despite performing 55% worse on IPM. **Recommendation: shift 80% of Static budget to Playable production; commission 3 new Playable variants (Chapter 3, 5, 7) for creative rotation.**

**2. T2 Brazil is the efficiency sweet spot - but we are underspending.**

Brazil delivers: CPI = £0.52, D1 retention = 34.2%, D7 ROAS = 8.1%. This outperforms T1 France (CPI = £3.40, D7 ROAS = 7.8%) on ROAS despite costing 85% less per install. The limiting factor is ad monetisation: T2 ARPDAU is £0.04 vs T1's £0.12. However, at £0.52 CPI, even modest ARPDAU justifies the spend.

**Recommendation: increase T2 Brazil daily budget by 40% (£72→£101/day), funded by reducing T3 India spend (where D7 ROAS is 3.2% and dropping).**

**3. TikTok Ads delivers 18% lower CPI than Meta - consistent with industry trend.**

GameBiz Consulting's 2026 data reports TikTok CPI is 15–25% below Meta for creative-heavy genres. Our data confirms this: TikTok T1 CPI = £2.32 vs Meta T1 CPI = £2.82 (18% gap). However, TikTok D7 retention is 2.1pp lower (15.3% vs 17.4%), suggesting the traffic is slightly lower-intent.

**Recommendation: scale TikTok budget by 25% for volume, but shift to ROAS-optimised bidding (not CPI) to protect retention quality. Test TikTok-native UGC-style creatives (reaction videos, "solve along with me" format).**

**4. iOS CPM premium is eroding T1 profitability.**

iOS CPM averages 22% above Android across all T1 markets. Combined with SKAN attribution limitations, iOS campaigns are harder to optimise. However, iOS users generate 35% higher ARPDAU (£0.14 vs £0.10).

**Recommendation: maintain iOS spend in T1 only; shift T2/T3 iOS budget entirely to Android where the CPM:ARPDAU ratio is more favourable.**

**5. Creative fatigue is measurable - the top creative has run 42 days without refresh.**

IPM for the Video 30s dropped from 11.8 in January to 8.4 in March - a 29% decline over the quarter. The creative fatigue cycle for puzzle games is 7–14 days (GameBiz 2026). Running a single creative for 42 days is a significant waste.

**Recommendation: establish a 10-day creative rotation cycle. Commission 2 new creatives per fortnight. Use A/B testing within Unity Ads and ironSource to measure IPM decay and swap at the 15% decline threshold.**

### ASO findings

Keyword `escape room game` (volume: 28,000/month) - we rank position 62, generating almost zero organic installs from this high-volume term. Competitor analysis shows Monday.com-level SEO effort is not needed - simply optimising the App Store subtitle and first screenshot to include "escape room" would improve ranking by an estimated 15–25 positions.

**Recommendation: update App Store listing - subtitle from "Rusty Lake's First Series" to "Escape Room Puzzle Adventure | 9 Chapters Free". Add keyword-optimised screenshot captions. Target position 30 for "escape room game" within 8 weeks.**

---

## Phase 4 - Prescriptive recommendations summary

| # | Action | Region | Expected impact | Timeline | Cost |
|---|---|---|---|---|---|
| 1 | Shift 80% of Static End Card budget → Playable production | All | -15% blended CPI, +22% IPM | Immediate | £0 (budget reallocation) |
| 2 | Commission 3 new Playable creatives (Ch3, Ch5, Ch7) | T1, T2 | Extend creative lifespan by 3× | 2 weeks to produce | £1,500–2,500 |
| 3 | Increase T2 Brazil daily budget by 40% | T2 | +1,200 installs/month at £0.52 CPI | Immediate | +£870/month |
| 4 | Reduce T3 India spend by 50% | T3 | Save £975/month; reinvest in T2 | Immediate | -£975/month |
| 5 | Scale TikTok by 25%, shift to ROAS bidding | T1, T2 | -18% CPI vs Meta at comparable retention | 1 week | +£1,200/month |
| 6 | 10-day creative rotation cycle | All | Prevent 29% IPM decay observed in Q1 | Ongoing process | £800/month (production) |
| 7 | ASO: update subtitle + screenshots | All (organic) | +500–800 organic installs/month | 1 week | £0 |
| 8 | Add 2nd rewarded ad placement per chapter | All | +15–20% ad revenue per session | 2 weeks (dev) | Dev time only |
| 9 | IAP: first-purchase discount (£0.99 starter pack) | T1 | IAP rate from 1.4% → 2.0% (benchmark: 1.83%) | 1 week | £0 |
| 10 | iOS budget: T1 only; T2/T3 Android only | T2, T3 | +8% ROAS in T2/T3 from better CPM:ARPDAU ratio | Immediate | £0 |

### Projected Q2 impact (if all recommendations implemented)

| Metric | Q1 actual | Q2 projected | Change |
|---|---|---|---|
| Blended CPI | £0.57 | £0.48 | -16% |
| Total installs | 91,770 | 108,000 | +18% |
| D7 ROAS (blended) | 10.0% | 13.5% | +35% |
| Ad revenue (Q2 total) | £5,253 | £7,800 | +48% |
| IAP revenue (Q2 total) | £1,480 | £2,200 | +49% |
