# DMIT Victoria: Specs, Real Pricing and Whether the $298.88/Year Hong Kong CN2 GIA Plan Deserves the Wait

Searching for "DMIT Victoria" usually means you've already heard the plan exists, and now you want three things: what's actually inside it, what it costs this month, and whether you can buy it at all. Those are reasonable questions, because Victoria is one of the few DMIT products that behaves more like a limited drop than a permanent catalogue item.

Here's what the plan is, what the numbers look like, and how it stacks up against the rest of the Hong Kong lineup.

## What "DMIT Victoria" Actually Refers To

Victoria is a Hong Kong VPS plan. Full name: **HKG.Pro.Victoria**, sometimes written PVM.HKG.Pro.Victoria, and it sits inside DMIT's Premium (Pro) network family — the tier built around China Telecom's CN2 GIA backbone rather than generic international transit.

DMIT itself has been selling KVM VPS since around 2017, registered in New York but heavily focused on Asian routes. It runs nodes in Hong Kong, Los Angeles, San Jose and Tokyo, and it's best known for buying quality Chinese-optimised bandwidth instead of reselling whatever transit is cheap that week.

The "Victoria" name is part of a pattern. DMIT's Hong Kong limited releases have historically carried Hong Kong place names, and Victoria is one of them, alongside labels like Mong Kok, Nathan, Lokmachau and Tsuen Wan. What separates Victoria from the regular Pro tiers (TINY, STARTER, MINI and friends) is that it's sold in limited batches, priced annually by default, and sits between the small Pro plans and the genuinely expensive ones on price-to-spec.

If you're comparing it to DMIT's mainstream Hong Kong Premium line, 👉 [check the current DMIT Hong Kong Premium lineup](https://www.dmit.io/aff.php?aff=12046) before you commit — that page is where you can see whether anything in the Victoria range is orderable right now.

## Victoria's specs, in one place

The current Victoria configuration, as listed across DMIT's product pages and third-party plan trackers:

| Item | Detail |
| --- | --- |
| vCPU | 1 |
| RAM | 2 GB |
| Storage | 60 GB SSD |
| Port | 500 Mbps VirtIO |
| Monthly traffic | 800 GB (counted in both directions) |
| IPv4 | 1 |
| IPv6 | 1 × /64 |
| Billing | $298.88/year, or $98.88/quarter |

Two things worth flagging here, because older guides still get them wrong.

The traffic allowance started at 500 GB/month and the disk at 40 GB on the first iteration. DMIT later refreshed the plan to 60 GB SSD and pushed the traffic cap to 800 GB without changing the $298.88 annual price. So if you find a review quoting 40 GB or 500 GB, it's describing the original batch, not the current one.

The port speed also moved. The first Victoria shipped at 300 Mbps; the version sold since then runs at 500 Mbps.

There's no separate bandwidth add-on and no unlimited-traffic option on this plan. When you burn through the 800 GB, DMIT doesn't cut the server off. It throttles the port down hard — the Pro series drops to roughly 4 Mbps, which is enough to keep SSH sessions alive and basically nothing else. T1 plans behave better here, throttling to somewhere between 50 Mbps and 1 Gbps depending on the tier, which is one reason the cheaper Hong Kong line has its own audience.

At 800 GB a month you're getting about 26 GB a day. For a single site with moderate traffic, a proxy for a handful of users, or a light application backend, that's comfortable. For anything streaming video to a group, it's tight.

## The network is the whole point

Nobody pays $298.88 a year for 1 vCPU and 2 GB of RAM. The reason Victoria exists is routing, and DMIT is unusually specific about it.

Inbound, China Telecom connects via CN2 GIA (the 59.43.x.x path) straight into Hong Kong, China Unicom enters through AS4837/AS10099, and China Mobile comes in over CMI. Outbound, all three carriers hand off through Hong Kong CTG into CN2 GIA on the way back. That's the "three-network CN2 GIA return" claim you'll see repeated in Chinese-language reviews, and it's the part that matters most for mainland visitors during evening peak hours.

Independent tests of DMIT's Hong Kong Premium network — the same class Victoria belongs to — generally land in the 40–55 ms range for mainland China. A few published measurements break down roughly as:

- China Telecom: about 42–45 ms
- China Unicom: about 39–42 ms
- China Mobile: about 46–61 ms

The mobile number is higher because the mobile inbound path transits through Japan before reaching Hong Kong. It's still fast, just not the lowest of the three. Packet loss in these tests is close to zero, including evening hours.

DMIT publishes Hong Kong test IPs in the 103.117.100.x range, so you can ping before you buy rather than trusting anyone's summary, including this one. If your latency comes back above 70 ms from your own connection, the problem is probably your local route and a $300/year plan won't fix it.

Two smaller details people ask about: the IPs are Hong Kong native, and replacing an IP costs $5.00, with Pro and Eyeball products getting one free replacement every 15 days.

## Price, billing cycles, and the codes people ask about

Victoria is quoted as **$298.88/year**, with a quarterly option at **$98.88**.

Run the math on that split. Four quarters come to $395.52, so paying annually saves roughly $96.64 compared with staying on quarterly billing. If you're confident you'll keep it for a year, the annual price is the obvious choice.

DMIT runs promo codes, but far fewer than most hosts in this niche, and codes are tied to specific product lines and billing periods. One that appears consistently across community listings is:

`202510_HKG_TYO_PRO_20OFF_RECURRING` — listed as 20% off, recurring, for Hong Kong and Tokyo Pro plans on quarterly or longer billing.

If it still applies to Victoria, that would take the annual price to around $239. Codes on this list rotate and expire without much notice, so enter it in the checkout field and hit validate before you assume anything. A recurring discount that sticks to renewals is worth considerably more than a one-time coupon, which is why DMIT's recurring codes get passed around so much in hosting forums.

Beyond that, DMIT sometimes runs account-targeted offers — extra traffic on semi-annual or annual orders, or discounts for existing customers — which show up inside the client area rather than on public landing pages. Worth checking after you register.

## Stock: why Victoria keeps disappearing

This is the part most articles skip, and it's the most practical thing to know.

Victoria is a limited release. DMIT has restocked it several times — batches have appeared across multiple years, typically announced with little warning and gone quickly — and one recent roundup noted that no restock had been announced for the limited Hong Kong plans at the time of writing, which puts Victoria in the "check availability, don't assume" category.

As of now, nothing in DMIT's public listings suggests Victoria is a permanent catalogue item. Practically, that means:

- Don't plan a project around buying Victoria next month
- If it's in stock and you need this routing, buying is a reasonable call
- If it isn't, the regular Hong Kong Pro plans deliver the same network, just at different price points

Second-hand demand is real, too. There are forum posts from buyers offering a premium above list price for Victoria accounts on recurring discounts, which tells you how the plan is regarded by people who use these servers for cross-border work.

## DMIT Hong Kong plans compared

Victoria only makes sense next to its neighbours, so here's the current Hong Kong lineup. DMIT also sells Los Angeles and Tokyo products; those are separate lineups with separate routing and aren't directly comparable.

**Hong Kong Premium (Pro) — CN2 GIA, mainland-optimised**

| Plan | vCPU | RAM | SSD | Port | Traffic | Price | Buy |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.Pro.Victoria (limited) | 1 | 2 GB | 60 GB | 500 Mbps | 800 GB/mo | $298.88/year or $98.88/quarter | [Check Victoria availability](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.TINY | 1 | 1 GB | 20 GB | 1 Gbps | 500 GB/mo | ~$39.9/month | [View the Pro TINY plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.STARTER | 1 | 2 GB | 40 GB | 1 Gbps | 1.0 TB/mo | ~$79.9/month | [View the Pro STARTER plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MINI | 2 | 2 GB | 60–80 GB | 1 Gbps | 1.5 TB/mo | ~$119.9–149.9/month | [View the Pro MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MICRO | 2 | 4 GB | 80–160 GB | 1 Gbps | 2 TB/mo | ~$159.9–179.9/month | [View the Pro MICRO plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MEDIUM | 4 | 4 GB | 160 GB | 1 Gbps | 2.5 TB/mo | ~$180–239.9/month | [View the Pro MEDIUM plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.LARGE | 4 | 8 GB | 240–320 GB | 1 Gbps | 3 TB/mo | ~$240/month | [View the Pro LARGE plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.GIANT | 8 | 16 GB | 320–640 GB | 1 Gbps | 6 TB/mo | ~$500/month | [View the Pro GIANT plan](https://www.dmit.io/aff.php?aff=12046) |

Two hardware generations are in circulation for Hong Kong Pro — AS3 (AMD EPYC 7003) and AN5 (EPYC 9005). Disk sizes and prices differ slightly between them, which is where the ranges above come from. Check which platform the order page shows before you buy, particularly if storage matters to your workload.

**Hong Kong Tier 1 — international BGP, not mainland-optimised**

| Plan | vCPU | RAM | SSD | Traffic | Price | Buy |
| --- | --- | --- | --- | --- | --- | --- |
| HKG.T1.WEE | 1 | 1 GB | 20 GB | 1 TB/mo | $36.9/year | [View the T1 WEE plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.TINY | 1 | 1 GB | 20 GB | 2 TB/mo | $53.83/year | [View the T1 TINY plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.STARTER | 1 | 2 GB | 40 GB | 4 TB/mo | $108.36/year | [View the T1 STARTER plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.MINI | 2 | 2 GB | 60 GB | 8 TB/mo | $183.96/year | [View the T1 MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.MICRO | 4 | 4 GB | 80 GB | 16 TB/mo | $276.36/year | [View the T1 MICRO plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.MEDIUM | 4 | 8 GB | 160 GB | 32 TB/mo | $419.16/year | [View the T1 MEDIUM plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.LARGE | 8 | 16 GB | 320 GB | 64 TB/mo | $839.16/year | [View the T1 LARGE plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.T1.GIANT | 8 | 24 GB | 640 GB | 128 TB/mo | $1679.16/year | [View the T1 GIANT plan](https://www.dmit.io/aff.php?aff=12046) |

Prices and stock on both tables shift with each restock, and DMIT has also listed a Hong Kong Eyeball (EB) line that has been in and out of inventory. Treat every number above as a starting point and confirm it on the order page.

## Who should actually buy Victoria

The clearest way to think about it: Victoria is the cheapest way to get DMIT's full Hong Kong Premium routing on an annual commitment.

Against the regular Pro line, that's the whole case. Victoria gives you 2 GB RAM and a 500 Mbps port for an effective $24.90 a month. HKG.Pro.STARTER asks roughly $79.9 a month and only matches Victoria's memory while giving you a 1 Gbps port and 1 TB of traffic. If you want DMIT's best mainland routing and 500 Mbps is enough, Victoria is dramatically cheaper per year than anything else in the Hong Kong Premium table.

Where it stops making sense:

- **You need a bigger port.** Victoria caps at 500 Mbps. Every regular Pro plan runs at 1 Gbps. If you're pushing sustained throughput, that gap matters more than the price difference.
- **You need more traffic.** 800 GB is decent for the money but the Pro tiers scale to 2.5 TB and 6 TB, and the T1 line goes far higher for a fraction of the cost.
- **Your users aren't in mainland China.** Tier 1 exists precisely for that. If your audience is European, American or Southeast Asian, HKG.T1.WEE at $36.9 a year is a better fit, and paying eight times more for CN2 GIA routing you'll never benefit from is waste.
- **You need serious compute.** 1 vCPU won't run a database-heavy application. This is a routing product with a small server attached, not the other way round.

The honest summary is that Victoria is a good deal for a narrow job: a Hong Kong server for mainland-facing traffic where low latency matters and the workload is light. Outside that box, other plans in the same lineup serve you better.

## Buying it: what the process looks like

Register an account, pick the plan, choose a billing cycle — annual if you plan to keep it — and apply any code you have before checkout. DMIT accepts Alipay, WeChat Pay, PayPal, credit cards and cryptocurrency, which covers most payment preferences for this audience.

After deployment you get a single IPv4 and a /64 IPv6 block, and you choose your OS image at order time. DMIT ships Linux images; Windows needs your own licensing and setup.

Two things to do in the first hour:

1. Ping the Hong Kong test IPs from your actual connection and from a couple of locations you care about. Don't take published latency numbers as a guarantee for your specific route.
2. Enable BBR if you're on an older kernel, and set up basic firewall rules. Less relevant for raw latency on CN2 GIA, more relevant for throughput on high-bandwidth transfers.

If you want to see what's orderable before committing to anything, 👉 [check current DMIT plans and pricing](https://www.dmit.io/aff.php?aff=12046) — that's the fastest way to find out whether Victoria or one of its neighbours is in stock today.

## FAQ

**Is DMIT Victoria the same as HKG.Pro.Victoria?**

Yes. "Victoria" is the shorthand; HKG.Pro.Victoria and PVM.HKG.Pro.Victoria are the full product names you'll see on order pages and in billing records.

**How much traffic does Victoria include now?**

800 GB per month, counted in both directions, up from 500 GB in the original release.

**Is it always available?**

No. It's a limited release that DMIT restocks in batches. Availability is unpredictable enough that you should check the order page rather than trusting any article, this one included.

**Can I use a discount code on it?**

DMIT issues codes per product line and billing period. `202510_HKG_TYO_PRO_20OFF_RECURRING` has been listed for Hong Kong and Tokyo Pro plans on quarterly-or-longer billing, but you need to validate it at checkout — codes expire, and whether a limited release qualifies can change.

**What happens when I exceed the traffic allowance?**

The port throttles rather than the server stopping. On Pro plans that means a very low speed, suitable for administration but not for serving traffic.

**Is Victoria worth $298.88 a year?**

If your visitors are mostly in mainland China, you need Hong Kong latency, and 1 vCPU with 800 GB of traffic is enough for your workload, it's the cheapest entry into DMIT's full Premium routing. If any of those don't apply, the Tier 1 line or a larger Pro plan will serve you better for less or similar money.
