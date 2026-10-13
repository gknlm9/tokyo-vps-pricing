# tokyo vps hosting: How to Pick the Right Route and Plan, and What a Tokyo Server Actually Costs

Most people searching for Tokyo VPS hosting already know they want a server in Japan. What they don't know is that the decision that actually matters — the one that determines whether their site feels fast or unusable — isn't the CPU count or the SSD size. It's the routing profile.

Two Tokyo VPS plans sitting in the same rack, running on the same hardware, can be signed under the same brand name and perform completely differently for a visitor in Shanghai, Seoul, or Frankfurt. One gets a dedicated premium path back to mainland China. The other goes out over plain international transit. The specs sheet looks nearly identical. The user experience doesn't.

So before you compare prices, it's worth understanding what you're actually paying for in Tokyo — and then working out which tier you need, because Tokyo is one of the more expensive places in Asia to buy compute.

## Why buy a Tokyo VPS in the first place

Tokyo is the lowest-latency major hub for a huge chunk of East Asia. Japan, Korea, Taiwan, and the coastal cities of China all sit within a few tens of milliseconds of a well-routed Tokyo box. For anyone in the region, that's roughly comparable to hosting domestically.

It also gives you infrastructure that parts of Asia can't easily provide: fast provisioning without lengthy registration processes, direct peering into JPNAP, JPIX, and BBIX (Japan's three main internet exchanges), and connectivity to carriers like NTT, KDDI, and SoftBank. If your audience is Japanese, or your business counts Japanese customers as an important segment, a Japan IP address is often what customers and partners expect to see.

The catch is price. Japan bandwidth isn't cheap, and premium routes to mainland China are the most expensive part of the bill. A Tokyo VPS with an optimized China route routinely costs several times a mid-range plan in the US or Europe. That's the trade you're making.

## Three questions before you look at a single plan

**Who is connecting?** If every visitor is in Japan or Korea, you don't need China routing at all, and paying for it is pure waste. If a meaningful share of your traffic comes from mainland Chinese ISPs, the routing question becomes the entire decision.

**How much traffic, and what happens when you exceed it?** This is where providers differ sharply. Some suspend the server when the quota runs out. Others throttle the port and keep you online with unlimited traffic — slower, but not down. For a production site, that difference matters more than $5/month.

**Do you need a Japanese IP specifically, or just low latency?** Plenty of businesses buy Tokyo purely as an Asia-Pacific relay point. Others genuinely need the Japan-registered address. Those are different purchasing decisions.

## The three routing profiles you'll see in Tokyo

Providers selling Tokyo capacity generally segment into tiers. The naming varies, but the structure is usually the same.

**Premium / China-optimized.** Your return path runs over premium Chinese carrier routes — typically China Telecom's CN2 GIA, China Unicom's AS9929 or AS10099, and China Mobile's CMI. CN2 GIA is a dedicated global internet access product from China Telecom; traffic travels on China Telecom's own backbone and avoids the public exchange points where congestion builds during Chinese evening peak hours. You pay a lot for it, and it's the reason some Tokyo plans cost upward of $100/month for modest compute.

**Eyeball / CMI-optimized.** A middle tier built around China Mobile's CMI network, generally friendlier to China Mobile subscribers. In Tokyo specifically, this tier has largely disappeared from the market — third-party trackers that monitor DMIT's stock report the Tokyo Eyeball line was pulled from sale, and it no longer appears in the shop. If you find an article recommending it, check the date.

**Tier 1 / international.** Plain global transit. No China optimization, but frequently bigger bandwidth ports and far better traffic allowances. This is the sane choice for anyone whose users aren't in mainland China.

## What DMIT actually sells in Tokyo

DMIT is a VPS provider running its own network with locations in Los Angeles, Hong Kong, and Tokyo. The Tokyo facility runs on the company's AS3 platform — AMD EPYC 7003 series processors, KVM virtualization, and SSD storage — and every plan includes one IPv4 address, an IPv6 /64 block, free setup, and DDoS protection.

The important detail is that DMIT's product descriptions state its Premium profile combines Tier 1 transit with premium providers including its own backbone and China Telecom's CN2 GIA. In other words, the company buys the underlying capacity directly rather than reselling someone else's optimized route. Whether that translates into a better experience for you is something you can test yourself before buying — DMIT publishes test IPs and a Looking Glass tool:

- Premium (Pro) test IP: `154.12.190.32`, Looking Glass at `lg.dmit.sh/?server=tyo-pro`
- Tier 1 (T1) test IP: `154.31.112.5`, Looking Glass at `lg.dmit.sh/?server=tyo-t1`

Ping those from wherever your users actually are. Ten minutes of testing beats any review you'll read, including this one. Note also that Tokyo stock moves constantly — certain plans go out of stock and reappear as IPs free up, so treat any availability figure as a snapshot.

### The traffic policy split is the real differentiator

This is where DMIT's two Tokyo lines diverge in a way that affects daily operations more than the spec sheet suggests.

**Premium plans suspend when you exceed the monthly quota.** Run through your 500 GB and the server stops until the cycle resets or you upgrade.

**Tier 1 plans throttle instead of cutting you off.** Exceed the allowance and the port drops to a reduced speed — 50 Mbps on the smallest plan, up to 1 Gbps on the largest — while traffic stays unlimited. If you've been throttled, the control panel has an overage mode you can toggle to apply the current bandwidth rules.

For a personal project, suspension is annoying. For a storefront, a streaming relay, or anything with paying users, unlimited-but-throttled is a fundamentally safer failure mode. It's worth paying attention to which one you're signing up for.

## Tokyo Premium (TYO.AS3.Pro) — full plan list

All Premium plans carry 1 Gbps ports, 1 IPv4 + 1 IPv6 /64, and suspend on quota overage.

| Plan | vCPU | RAM | SSD | Monthly traffic @ port | Price (USD) | Order |
| --- | --- | --- | --- | --- | --- | --- |
| TYO.AS3.Pro.TINY | 1 | 1.0 GB | 20 GB | 500 GB @ 1 Gbps | $21.90/mo | [ Check current TINY stock and pricing](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.STARTER | 1 | 2.0 GB | 40 GB | 1,000 GB @ 1 Gbps | $45.90/mo | [ See the STARTER plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.MINI | 2 | 4 GB | 60 GB | 2,000 GB @ 1 Gbps | $89.90/mo | [ See the MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.MICRO | 4 | 4 GB | 80 GB | 4,000 GB @ 1 Gbps | $189.90/mo | [ See the MICRO plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.MEDIUM | 4 | 8 GB | 160 GB | 5,000 GB @ 1 Gbps | $320.90/mo | [ See the MEDIUM plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.LARGE | 8 | 16 GB | 320 GB | 8,000 GB @ 1 Gbps | $429.90/mo | [ See the LARGE plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.Pro.GIANT | 8 | 24 GB | 640 GB | 15,000 GB @ 1 Gbps | $829.90/mo | [ See the GIANT plan](https://www.dmit.io/aff.php?aff=12046) |

Read those numbers again with fresh eyes. $89.90 a month buys you a 2-core, 4 GB box. That is not a typo, and it's not a DMIT-specific problem — it's what a genuinely optimized Tokyo route costs. You're buying the network, and the compute is almost a rounding error.

That framing also tells you who should buy Pro and who shouldn't. If your visitors are in Japan, Korea, or anywhere outside mainland China, the premium route is invisible to them. You'd be paying four to five times the necessary price for a benefit nobody experiences. Buy Tier 1 instead and spend the difference on something useful.

Pro makes sense in a fairly narrow band of situations: you need a Japan IP *and* fast, stable access from Chinese ISPs; you're running a cross-border e-commerce store, a remote-work gateway, a game accelerator, or a media relay serving both sides; or you have multiple regional nodes and want Tokyo as the Asia-Pacific anchor. Outside that band, go look at the next table.

## Tokyo Tier 1 (TYO.AS3.T1) — full plan list

Tier 1 runs on the same AMD EPYC 7003 hardware over international transit. Traffic overage throttles rather than suspends, and ports are wider — 4 Gbps on the two smallest plans, 10 Gbps from STARTER upward.

| Plan | vCPU | RAM | SSD | Monthly traffic @ port | Overage | Price (USD) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.AS3.T1.WEE | 1 | 1 GB | 20 GB | 1 TB @ 4 Gbps | 50 Mbps, unlimited | $36.90/year | [ Check WEE availability](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.TINY | 1 | 2 GB | 40 GB | 2 TB @ 4 Gbps | 100 Mbps, unlimited | $6.90/mo | [ See the TINY plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.STARTER | 2 | 2 GB | 40 GB | 4 TB @ 10 Gbps | 100 Mbps, unlimited | $12.90/mo | [ See the STARTER plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.MINI | 2 | 4 GB | 80 GB | 8 TB @ 10 Gbps | 100 Mbps, unlimited | $21.90/mo | [ See the MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.MICRO | 4 | 4 GB | 80 GB | 16 TB @ 10 Gbps | 200 Mbps, unlimited | $32.90/mo | [ See the MICRO plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.MEDIUM | 4 | 8 GB | 160 GB | 32 TB @ 10 Gbps | 200 Mbps, unlimited | $49.90/mo | [ See the MEDIUM plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.LARGE | 8 | 16 GB | 320 GB | 64 TB @ 10 Gbps | 500 Mbps, unlimited | $99.90/mo | [ See the LARGE plan](https://www.dmit.io/aff.php?aff=12046) |
| TYO.AS3.T1.GIANT | 8 | 24 GB | 640 GB | 128 TB @ 10 Gbps | 1 Gbps, unlimited | $199.90/mo | [ See the GIANT plan](https://www.dmit.io/aff.php?aff=12046) |

The WEE plan only sells on annual billing. TINY is also commonly listed with an annual option around $76.90, which works out cheaper than twelve monthly payments if you're confident you'll keep it.

The value story here is almost comically different from the Pro table. T1.TINY gives you 2 GB of RAM, 40 GB of SSD, and 2 TB of traffic on a 4 Gbps port for $6.90 a month. Compare that to Pro.TINY at $21.90 for 1 GB, 20 GB, and 500 GB. You are paying roughly triple for *less* — because with Pro you're buying the route, and with T1 you're buying capacity.

One honest qualifier on the T1 routing: it's international transit, which means your path from China can go over NTT both directions, and at times traffic may detour through the US via Lumen before reaching Japan. If a chunk of your audience is in mainland China, that's a real performance hit you'll notice in the evening. If they're not, it's irrelevant.

## There's also a promotional Shinagawa plan

Alongside the standard lineup, DMIT periodically lists a discounted TYO.Pro "Shinagawa" plan: 1 vCPU, 2 GB RAM, 60 GB SSD, 500 Mbps bandwidth, priced at $239.90/year or $69.90/quarter, with quarterly and annual billing only. Third-party listings disagree on the monthly traffic allowance — some say 500 GB, others 800 GB — so confirm the figure on the order page rather than trusting any secondary source, including this one. The specs and pricing are the parts that agree.

If that configuration fits your needs, it's a meaningfully cheaper way into the Premium route than the standard STARTER plan at $45.90/month.

## Discount codes: worth testing, worth verifying

DMIT doesn't run the constant sitewide sales some budget hosts do. Its promo codes are fewer, tied to specific product lines and billing cycles, and often time-limited. Codes circulating publicly include:

- `2025-TYO-T1-HI-GSL-NON-MONTHLY-30OFF` — 30% off Tokyo T1 plans from TINY upward on quarterly billing or longer, applied as a recurring discount
- `2025-TYO-T1-HI-GSL-MONTHLY-10OFF` — 10% off the same plans on monthly billing
- `202510_HKG_TYO_PRO_20OFF_RECURRING` — 20% recurring discount on Hong Kong and Tokyo Pro plans on quarterly billing or longer
- `202510_HKG_TYO_T1_30OFF_RECURRING` — 30% recurring discount on Hong Kong and Tokyo T1 plans on quarterly or longer billing, excluding WEE
- `2025-TYO-PRO-HI-GSL-ANNUALLY-20OFF` — 20% recurring discount on annual Tokyo Pro orders
- `2025-EXISTING-CUSTOMER-10OFF` — 10% off for existing customers whose cumulative monthly spend exceeds $3.33

Two things to note before you get excited. First, the pattern is consistent: monthly billing rarely qualifies for the big discounts. You have to commit to a quarter or a year to trigger most of these. Second, codes expire. Some of the T1 promotions were published with specific end dates that have long passed. Paste the code into the checkout page and watch the total change — if the discount applied, you'll see it immediately. If nothing happens, it's dead. Never assume a code still works because a blog published it.

The recurring part is what makes these worth chasing: a recurring percentage discount applies to every renewal, not just the first invoice, which over a multi-year horizon is considerably more than it sounds.

## Which Tokyo plan should you actually buy

If you're hosting for Japanese, Korean, or general international users, start with **T1.STARTER** at $12.90/month. Two cores, 2 GB of RAM, 4 TB of traffic on a 10 Gbps port, and unlimited throttled traffic instead of a hard suspension. It handles a WordPress site, a small API, a Docker host, or a game server without drama.

If you need a Japan IP for a lightweight project and want to spend almost nothing, **T1.TINY** at $6.90/month or **T1.WEE** at $36.90/year are about as cheap as Tokyo gets from a provider running its own hardware.

If mainland China performance is the whole point — e-commerce, remote access, acceleration, relay — then **Pro.TINY** at $21.90/month is the entry point, and you should accept that the compute you get for that money is small. The route is the product. If you need real headroom *and* the premium route, the step up to STARTER or MINI gets expensive fast, and it's worth asking whether a Hong Kong node would serve you better before committing.

And if you're provisioning a cluster or running media workloads, the Pro tiers above MINI are enterprise-priced. At $320.90/month for 4 cores and 8 GB, most teams should be evaluating colocation or a dedicated server instead. Nobody should reach that tier by accident.

## Before you order

Four things worth doing, in order. Ping the test IPs from the locations your users are in, and if you can't test directly, run a traceroute from a vantage point in mainland China during evening peak hours. Check the current stock on the order page, since Tokyo inventory fluctuates and low-cost plans sell out first. Decide on the billing cycle before you look at prices, because the meaningful discounts only exist above monthly. And confirm the traffic policy on the exact plan you're buying — suspension and throttling are very different commitments when something goes wrong at 2 a.m.

Tokyo hosting is expensive, and the route is what you're buying. Get the route decision right and the rest of the plan barely matters. Get it wrong and you've paid a premium for a benefit your users never experience.

[👉 Browse every Tokyo plan and current availability on DMIT](https://www.dmit.io/aff.php?aff=12046)
