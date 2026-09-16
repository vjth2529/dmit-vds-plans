# virtual dedicated server: dedicated-grade resources at a fraction of the cost, and a full comparison of DMIT's LAX, Hong Kong, and Tokyo plans

If you've ever stared at a hosting provider's pricing page and tried to figure out whether you need a "virtual dedicated server," a "VPS," or something else entirely, you're not alone. The terms get thrown around interchangeably, sometimes by the same company on the same page, and the marketing copy rarely helps. This article breaks down what a virtual dedicated server actually is, where it sits between a VPS and a bare-metal box, and then walks through a concrete set of plans you can actually buy today — specifically DMIT's cloud instance lineup across Los Angeles, Hong Kong, and Tokyo — so you have real specs, real prices, and real trade-offs to compare instead of adjectives.

## What "virtual dedicated server" actually means

A virtual dedicated server (VDS) is a virtual machine running on a hypervisor sitting on top of physical hardware, but sold and provisioned in a way that emphasizes dedicated, guaranteed resources for the tenant. The distinction from a generic VPS is mostly about how the underlying CPU, RAM, and I/O are allocated: a VPS may share resources more loosely with neighbors on the same host, while a VDS is positioned as giving you a fixed slice that behaves more like your own machine.

In practice, the line between the two has blurred. Wikipedia notes that "virtual private server (VPS) or virtual dedicated server (VDS)" are treated as interchangeable terms for "a virtual machine sold as a service by an Internet hosting company." OVHcloud's glossary frames VDS as offering "dedicated resources for greater control and performance." Different vendors draw the boundary differently, and some don't draw one at all.

What matters when you're shopping is not the label but the actual guarantee:

- Whether your CPU cores are dedicated or shared
- Whether RAM is reserved or burstable
- Whether disk I/O is isolated from noisy neighbors
- Whether the network port is a hard cap or "up to" a peak

A well-provisioned VPS with dedicated vCores and reserved RAM will behave like a VDS. A poorly provisioned one sold as "VDS" won't. Read the spec sheet, not the badge.

## VDS vs VPS vs dedicated: where each one sits

A physical dedicated server gives you the entire box — all cores, all RAM, all disks, all NICs, no hypervisor overhead. You pay for that exclusivity, and you pay for the fact that you can't scale it down on a Tuesday afternoon. Prices start in the low hundreds per month for entry-level hardware and climb fast.

A VPS or VDS carves that box into virtual machines. You get root access, your own OS, your own kernel, and isolation from other tenants — but you're sharing the physical host. The upside is price, flexibility, and deployment speed. The downside is that "dedicated resources" on a VM is never quite the same as having the silicon to yourself; there's always a hypervisor in the middle, and there's always some shared component (the storage controller, the network fabric, the host's NIC).

A shared hosting account, for completeness, doesn't give you a server at all — you get a slice of a server's web stack, no root, no OS choice, no isolation beyond file permissions.

So the practical decision tree is:

- **Shared hosting** when you're running a low-traffic WordPress site and don't want to touch a terminal.
- **VPS / VDS** when you need root, want to run custom software, or have outgrown shared hosting but can't justify a whole box.
- **Dedicated** when you have a sustained, predictable workload that genuinely needs all the cores and all the RAM, or has compliance requirements that rule out multi-tenancy.

Most people reading about "virtual dedicated server" are in the middle bucket. That's the bucket DMIT lives in.

## Where DMIT fits

DMIT is a hosting provider operating out of Los Angeles, Hong Kong, and Tokyo, running KVM virtual machines on AMD EPYC platforms. Their pitch is not "cheapest VM on the internet" — it's "engineered network routing, particularly into mainland China, on hardware that doesn't cut corners." If you've never cared about CN2 GIA or CMIN2 transit, half their marketing won't mean much to you. If you're building something where users in China or the broader Asia-Pacific region need a fast, low-loss path to your server, those words matter a lot.

Every plan DMIT sells comes in three network flavors, and the flavor matters more than the tier in a lot of cases:

**Premium Network** combines Tier 1 transit with premium partners including DMIT's own backbone and China Telecom CN2 GIA. This is the top-tier routing for China-facing and APAC-facing workloads. Expect lower latency, fewer hops, and less packet loss than standard internet paths. It's also the most expensive.

**Eyeball Network** pairs Tier 1 transit with "reasonable effort" China routing via CMIN2 and other Chinese eyeball ISPs. It's a middle ground — noticeably better access for Chinese residential users than plain Tier 1, but without the premium routing guarantees. Priced accordingly.

**Tier 1 Network** is clean, optimized routing across APAC and the Americas with no specific China-routing work. It's the cheapest series, and the right one if your users are mostly outside China or you just need raw bandwidth and a stable IP.

On the hardware side, DMIT runs three platforms. The **AN5** series uses AMD EPYC 9005 (Zen 5) with DDR5 and PCIe 5.0 NVMe — their flagship, best for latency-sensitive and high-traffic workloads. The **AN4** series uses EPYC 9004 (Zen 4), a proven balanced platform. The **AS3** series uses EPYC 7003 (Zen 3), the value tier. Note from the official LA page: "The LAX AS3 series is still being built out and optimized. During this period you may experience reduced disk performance and a lower SLA than our mature platforms." Worth knowing before you buy the cheapest option.

## The full plan lineup

Below is every plan DMIT currently lists on their official pricing and location pages, organized by data center and network series. Prices are the starting monthly rate as shown on the official pages; annual billing is available and typically reduces the effective per-month cost, and select promo codes (more on those below) stack on top.

If you want to look at the live ordering page directly, you can 👉 [check the current DMIT plan list here](https://bit.ly/DmiT).

### Los Angeles (LAX)

LAX is DMIT's flagship location, sitting in the CoreSite and Digital Realty LA campuses with 3.8 Tbps of aggregate Tier 1 capacity and direct high-capacity peering to China Telecom (AS4809), China Unicom (AS9929), and China Mobile International (AS58807).

**Premium Network (AS3 platform):**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 | 2GB | 20GB | 1000GB | 1Gbps | $10.90 | [Buy](https://bit.ly/DmiT) |
| Pocket | 2 | 2GB | 40GB | 1500GB | 4Gbps | $16.90 | [Buy](https://bit.ly/DmiT) |
| STARTER | 2 | 2GB | 80GB | 3000GB | 10Gbps | $34.90 | [Buy](https://bit.ly/DmiT) |
| MINI | 4 | 4GB | 80GB | 5000GB | 10Gbps | $62.90 | [Buy](https://bit.ly/DmiT) |
| MICRO | 4 | 4GB | 160GB | 7000GB | 10Gbps | $87.90 | [Buy](https://bit.ly/DmiT) |
| MEDIUM | 6 | 8GB | 160GB | 15000GB | 10Gbps | $199.90 | [Buy](https://bit.ly/DmiT) |

**Eyeball Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.EB.STARTER | 2 | 2GB | 80GB | 5000GB | 10Gbps | $29.90 | [Buy](https://bit.ly/DmiT) |
| LAX.EB.MINI | 4 | 4GB | 80GB | 10000GB | 10Gbps | $58.88 | [Buy](https://bit.ly/DmiT) |
| LAX.EB.MICRO | 4 | 4GB | 160GB | 14000GB | 10Gbps | $74.99 | [Buy](https://bit.ly/DmiT) |

**Tier 1 Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.T1.STARTER | 1 | 2GB | 40GB | 4000GB (IN+OUT) | Performance-based | $12.90 | [Buy](https://bit.ly/DmiT) |
| LAX.T1.MINI | 2 | 2GB | 60GB | 8000GB (IN+OUT) | Performance-based | $21.90 | [Buy](https://bit.ly/DmiT) |
| LAX.T1.MICRO | 4 | 4GB | 80GB | 16000GB (IN+OUT) | Performance-based | $32.90 | [Buy](https://bit.ly/DmiT) |

A couple of things jump out from the LAX lineup. The Premium TINY at $10.90 is the cheapest entry point, but it's on the still-being-optimized AS3 platform and capped at 1Gbps with 1TB of transfer. The Eyeball STARTER at $29.90 gives you the same 2 vCores and 2GB RAM but 5TB of transfer on a 10Gbps port — meaningfully more bandwidth headroom for less than 3x the price. If your workload is bandwidth-bound rather than China-latency-bound, Tier 1 is absurdly cheap per TB: $32.90 gets you 16TB of transfer on 4 cores and 4GB.

### Hong Kong (HKG)

Hong Kong is where latency-sensitive APAC and China-facing workloads often want to live. The Premium plans here are pricier than LAX and capped at 1Gbps ports, reflecting the cost of premium HK bandwidth.

**Premium Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.Pro.STARTER | 1 | 2GB | 40GB | 800GB | 1Gbps | $79.90 | [Buy](https://bit.ly/DmiT) |
| HKG.Pro.MINI | 2 | 2GB | 60GB | 1200GB | 1Gbps | $119.90 | [Buy](https://bit.ly/DmiT) |
| HKG.Pro.MICRO | 4 | 4GB | 80GB | 1600GB | 1Gbps | $159.90 | [Buy](https://bit.ly/DmiT) |

**Eyeball Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.EB.STARTERv2 | 1 | 2GB | 40GB | 2000GB | 2Gbps (no guarantee) | $59.90 | [Buy](https://bit.ly/DmiT) |
| HKG.EB.MINIv2 | 2 | 2GB | 60GB | 3000GB | 2Gbps (no guarantee) | $89.90 | [Buy](https://bit.ly/DmiT) |
| HKG.EB.MICROv2 | 4 | 4GB | 80GB | 4000GB | 4Gbps (no guarantee) | $129.90 | [Buy](https://bit.ly/DmiT) |

**Tier 1 Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.T1.STARTER | 1 | 2GB | 40GB | 4000GB (IN+OUT) | Performance-based | $12.90 | [Buy](https://bit.ly/DmiT) |
| HKG.T1.MINI | 2 | 2GB | 60GB | 8000GB (IN+OUT) | Performance-based | $21.90 | [Buy](https://bit.ly/DmiT) |
| HKG.T1.MICRO | 4 | 4GB | 80GB | 16000GB (IN+OUT) | Performance-based | $32.90 | [Buy](https://bit.ly/DmiT) |

The HKG Tier 1 plans are priced identically to LAX Tier 1 — same $12.90 / $21.90 / $32.90, same specs. That's the cheapest way into Hong Kong bandwidth on DMIT, with the obvious caveat that you're giving up China-optimized routing. The Eyeball v2 series explicitly notes "no guarantee" on the port speed, which is honest labeling — it means DMIT will try to give you 2 or 4Gbps but won't commit to it contractually.

### Tokyo (TYO)

Tokyo rounds out the trio, useful for Japan-facing workloads and as a low-latency APAC hub. The Premium STARTER at $39.90 is the cheapest Premium entry across all three locations.

**Premium Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.Pro.STARTER | 1 | 2GB | 40GB | 500GB | 1Gbps | $39.90 | [Buy](https://bit.ly/DmiT) |
| TYO.Pro.MINI | 2 | 2GB | 60GB | 1000GB | 1Gbps | $79.90 | [Buy](https://bit.ly/DmiT) |
| TYO.Pro.MICRO | 4 | 4GB | 80GB | 2000GB | 1Gbps | $159.90 | [Buy](https://bit.ly/DmiT) |

**Eyeball Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.EB.STARTER | 1 | 2GB | 40GB | 2000GB | 2Gbps (no guarantee) | $55.90 | [Buy](https://bit.ly/DmiT) |
| TYO.EB.MINI | 2 | 2GB | 60GB | 3000GB | 2Gbps (no guarantee) | $85.90 | [Buy](https://bit.ly/DmiT) |
| TYO.EB.MICRO | 4 | 4GB | 80GB | 4000GB | 4Gbps (no guarantee) | $119.90 | [Buy](https://bit.ly/DmiT) |

**Tier 1 Network:**

| Plan | vCores | RAM | SSD | Transfer | Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TYO.T1.STARTER | 1 | 2GB | 40GB | 4000GB (IN+OUT) | Performance-based | $12.90 | [Buy](https://bit.ly/DmiT) |
| TYO.T1.MINI | 2 | 2GB | 60GB | 8000GB (IN+OUT) | Performance-based | $21.90 | [Buy](https://bit.ly/DmiT) |
| TYO.T1.MICRO | 4 | 4GB | 80GB | 16000GB (IN+OUT) | Performance-based | $32.90 | [Buy](https://bit.ly/DmiT) |

The Tier 1 trio is again identical in price and spec to LAX and HKG — DMIT clearly standardized the Tier 1 entry tier across regions, which makes cross-region comparisons easy.

## What every plan includes

Across the entire lineup, regardless of location or network series, DMIT bundles the same baseline:

- **KVM virtualization** with full root access
- **1 IPv4 and 1 IPv6 /64** address (Premium LAX plans list "1 IPv4 & 1 IPv6 /64"; other locations list "1 IPv4 & 1 IPv6")
- **Basic DDoS protection** included
- **Free instant setup** — instances deploy in minutes
- **Auto-rebalance deployment** across DMIT's nodes within a location, so a noisy neighbor on one host gets mitigated by spreading instances
- **One-touch OS installation** for Ubuntu, CentOS, Debian, and CloudLinux; ISO mount for anything else
- **Snapshots** of running instances, reloadable anytime
- **Online backup** as a paid add-on starting at $0.45/GB per month

The official SLA is 99% uptime. Per their TOS, if actual uptime drops below 99% you get half a month's credit; below 95% a full month; below 90% two months. That's not a five-nines promise, and it's worth setting expectations accordingly — DMIT is upfront that they target 99%, not 99.99%.

Support is explicitly unmanaged: the TOS notes they "can only guarantee the support ticket reply with 72 hours." If you need hands-on management or fast response times on infrastructure issues, that's a real consideration. This is a provider aimed at people who are comfortable running their own Linux box.

## Promo codes and how to actually save

DMIT runs periodic promotions and releases discount codes, typically tied to events. The 2025 Christmas promotion — which offered 15–20% recurring discounts plus 5–10% account cashback on LAX Pro, EB, and T1 plans — has officially ended, so those specific codes should be treated as expired.

What does reliably help:

- **Annual billing** unlocks better per-month pricing and is required for most promo codes. The general pattern across hosting providers (DMIT included) is that committing to a year knocks roughly 10–20% off the equivalent monthly rate, before any code.
- **Region-specific recurring codes** appear on DMIT's own event pages and on third-party coupon aggregators. As of the time of writing, codes referenced on coupon sites include things like 20% recurring on LAX T1 annual plans and similar discounts for HKG and TYO T1 annual plans. These come from third-party sources and I can't verify their current validity on DMIT's official checkout — always paste the code into the cart and confirm the discount applies before paying.
- **Referral rewards** are doubled during promotional windows per DMIT's event terms, which matters if you're already an affiliate or are referred by one.

The practical advice: check the 👉 [current DMIT offers page](https://bit.ly/DmiT) for whatever promotion is live right now, default to annual billing if you're confident about the workload, and never pay monthly if a code you want requires annual — you'll lose the discount and pay more in the long run.

## How to pick between the plans

The "which plan" question is really three separate questions stacked on top of each other.

**First: which location?** That's answered by where your users are. China and APAC users benefit from HKG or TYO; a primarily North American audience is fine on LAX; a globally distributed audience usually wants LAX as the hub because of its 3.8 Tbps of Tier 1 capacity and dense peering. If you're running a VPN or proxy and the endpoint needs to reach China specifically, HKG Premium or LAX Premium are the two serious options.

**Second: which network series?** Premium if China routing quality is the priority and budget allows. Eyeball if you want decent China reach without paying Premium prices. Tier 1 if China isn't in your user base at all and you just want cheap, fast, well-routed bandwidth. The price gaps are large — HKG Premium STARTER is $79.90, HKG Tier 1 STARTER is $12.90 — so don't buy Premium unless the routing actually matters to your workload.

**Third: which tier within the series?** This is pure resource sizing. The jump from STARTER to MICRO roughly doubles cores and RAM and multiplies transfer. The LAX Premium MEDIUM at $199.90 with 6 vCores, 8GB RAM, and 15TB is the most "server-like" of the entry lineup and is where you start approaching dedicated-box territory in terms of usable headroom. Below that, you're in VM territory — fine for most web workloads, APIs, build servers, and dev environments, but not for a heavy database under load.

A reasonable rule of thumb: start one tier lower than you think you need, monitor actual CPU and RAM usage for a billing cycle, and upgrade only if you're consistently hitting limits. DMIT allows upgrades (with possible modification fees per their TOS), and downgrades effectively mean re-initiating service. Better to size up than to overpay from day one.

## Refund and IP policies worth knowing

A few TOS clauses directly affect buying decisions:

- **Refunds**: full refund (minus payment gateway fees) within 3 days and under 30GB of transfer used. Partial refund within 30 days, calculated on either remaining transfer or remaining time, whichever is lower. No refunds after 3 prior refunds on the same product series, no refunds if you've been DDoSed, no refunds for "network not good enough" or IP geo-location complaints, and no refunds if you initiate a payment dispute in violation of TOS.
- **IP replacement**: on Premium and Eyeball, free replacement every 15 days without the `IP Care+` add-on, every 7 days with it, or $5 for immediate replacement anytime. On Tier 1, $5 per replacement with 7 days between, unless you have the `IP Guarantee+` add-on. New orders within 7 days and services with under 7 days remaining are charged the replacement fee regardless.
- **Fair use**: DMIT reserves the right to rate-limit, reprice to standard bandwidth rates, or suspend service for usage patterns they deem outside "normal, fair, and reasonable use." This is standard hosting language but means sustained maxed-out 10Gbps 24/7 will get a conversation, not silence.
- **OFAC restrictions**: no orders from Cuba, Iran, Lebanon, Libya, Myanmar, North Korea, Somalia, Sudan, or Syria.

If you're planning to run anything bandwidth-heavy or unusual, read the AUP before buying rather than after.

## Who should actually buy a DMIT plan

DMIT is not the cheapest VM provider on the internet. Hetzner, OVH, and Contabo will beat them on raw price-per-GB-of-RAM for generic workloads, and anyone telling you otherwise is selling something. What DMIT sells is routing quality — specifically, the difference between a packet that takes 12 hops and 180ms to reach a Shanghai residential user versus one that takes 4 hops and 40ms over CN2 GIA. If that difference doesn't matter to you, you're overpaying.

If it does matter — you run a China-facing e-commerce site, a media platform with APAC viewers, a game server with Asian players, or a VPN endpoint where connection quality into China is the entire product — then the Premium series is priced competitively for what it actually delivers, and the Eyeball series is a sensible middle ground.

For everyone else: the Tier 1 series at $12.90 / $21.90 / $32.90 across LAX, HKG, and TYO is a genuinely good deal on well-routed bandwidth in three solid data centers, with the caveat that you're buying into an unmanaged provider with a 72-hour support ticket SLA. If you can administer your own box and want a clean network at a low price, it's worth a look. If you need hand-holding, look elsewhere.

## Quick FAQ

**Is a DMIT cloud instance a "virtual dedicated server" or a "VPS"?**
Technically a VPS — KVM-based VMs on shared hosts. But the Premium and Eyeball tiers provision dedicated vCores and reserved RAM, which puts them in VDS territory in terms of how the resources actually behave. The label matters less than the spec sheet.

**Can I run Windows?**
DMIT's one-touch installer covers Linux distributions (Ubuntu, CentOS, Debian, CloudLinux). For Windows or other OSes, you'd need to mount an ISO and install manually. Check the official ordering page for current OS support before committing.

**Do the prices include tax?**
Per DMIT's TOS, "you agree to pay any and all taxes, including personal property, value added, or sales taxes, resulting from your use of the Services." Listed prices are pre-tax.

**Can I upgrade mid-cycle?**
Yes, but per the TOS, upgrades and downgrades "may include modification fees or require reinitiating service." Contact their sales team for specifics on your plan.

**What happens if I exceed my transfer quota?**
Per the TOS, you can choose to reset, suspend, or be speed-limited. On the Christmas event fine print (which reflects general policy), once transfer is exhausted the port is throttled to a lower rate and resets the following month, with unlimited transfer within reasonable use after throttling. Don't plan to sustain peak bandwidth 24/7.

**Is the 10Gbps port real?**
DMIT's own fine print says port speeds are "VirtIO port peak speeds" and "actual speeds are limited by VM performance, international and local network conditions," so the listed port speed is a ceiling, not a guarantee. Expect real-world throughput well below the headline number on smaller plans.

If you want to look at the current pricing and ordering flow directly, 👉 [head to the DMIT plan page](https://bit.ly/DmiT) and configure an instance for the location and network series that fits your workload.
