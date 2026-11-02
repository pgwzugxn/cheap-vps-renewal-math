# cheap vps: what $21.99 a year actually buys you, how the renewal math works, and which plan fits your project

Everyone searching for a cheap VPS eventually runs into the same trap: a $2/month intro price that quietly doubles at renewal. So the honest answer up front — the cheapest *usable* VPS isn't the one with the lowest first invoice, it's the one with the lowest **renewal** price. That's why this guide focuses on RackNerd's annual KVM specials, which start at **$21.99/year** (about $1.83/month) for 1GB RAM and renew at the same price, officially labeled "lifetime recurring" on the specials page.

> **Quick picks**
> - Just need a playground or a small site: the **1GB plan at $21.99/year** is fine for a blog, a bot, or a lightweight self-hosted service.
> - Running a real website or automation tools: get the **2GB plan at $35.99/year** — it's the plan most people should actually buy.
> - Want to run local AI tools like Ollama or AnythingLLM: you need at least **4GB ($59.99/year)**.
> - Check current stock and locations here: 👉 [view all RackNerd annual VPS specials](https://bit.ly/RacKnerd)

## RackNerd's full annual VPS lineup

These are the five KVM VPS specials currently listed on the official specials page. All plans share the same basics: KVM virtualization with dedicated resources, full root access, 1 dedicated IPv4, a 1Gbps port, and instant provisioning after payment. All prices are annual, in USD.

| Plan | CPU / RAM | SSD | Monthly traffic | Price | Buy |
| --- | --- | --- | --- | --- | --- |
| 1 GB KVM | 1 core / 1 GB | 20 GB | 3 TB | $21.99/yr | [ order the 1GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=952) |
| 2 GB KVM | 2 cores / 2 GB | 35 GB | 5 TB | $35.99/yr | [ order the 2GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=953) |
| 4 GB KVM | 3 cores / 4 GB | 60 GB | 7 TB | $59.99/yr | [ order the 4GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=954) |
| 6 GB KVM | 6 cores / 6 GB | 100 GB | 12 TB | $89.99/yr | [ order the 6GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=955) |
| 8 GB KVM | 7 cores / 8 GB | 150 GB | 20 TB | $119.99/yr | [ order the 8GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=956) |

The 1GB plan carries a "Most popular" tag on the official page. Fair enough — but keep reading before you click it, because "popular" and "right for you" aren't always the same thing.

## The renewal math most cheap VPS articles skip

Here's the number that matters more than the sticker price: what you'll pay in year two and year three.

RackNerd's specials are **lifetime recurring** — the official page states it directly. Pay $35.99 for the 2GB plan this year, and next year's invoice is also $35.99. Three-year cost: about $108.

Compare that with the cheapest name-brand option. According to Cybernews's August 2026 roundup of budget VPS providers, IONOS starts at $2.00/month for its VPS XS (1 vCPU, 1GB RAM, 10GB NVMe), but its VPS M jumps from $4.00/month to **$8.00/month on renewal** — that's $96 in year two for 4GB RAM. Cybernews puts the industry pattern plainly: *"Many VPS hosting providers offer cheaper entry plans before raising the price for future use."*

Vultr plays a different game altogether: its cloud compute plans bill **hourly** — the monthly fee is divided across 672 hours (a 28-day month), and your total is capped at the monthly rate. Its cheapest regular plan with an IPv4 address runs $5.00/month for 1 vCPU, 1GB RAM, and 25GB SSD. Two quirks matter if you go that route. First, **stopping an instance doesn't stop the billing** — a stopped server still holds its RAM, disk, CPU allocation, and IP, so charges keep accruing until you actually destroy the instance. Second, bandwidth is prorated by the hour, so if you burn through your monthly allowance in a burst and then delete the server, the overage gets billed separately — and overage rates in Asia-Pacific regions run several times the North American price. For always-on boxes this is workable, but it's a billing model that punishes inattention.

Neither model is a scam. IONOS bundles a 30-day money-back guarantee, a 99.99% uptime commitment, and phone support, and those things cost money. But if your decision rule is "lowest total cost over 2–3 years for a self-managed box that runs 24/7," the annual-renewal-same-price model usually wins, and it's worth calculating before you commit to any provider. One long-time RackNerd user summed up the appeal simply: costs work out to roughly **$1 per GB of RAM per month**.

## What you can actually run on each plan

RackNerd's own FAQ is unusually specific about this, and it's the best basis for choosing a plan. The ctrl control panel includes one-click apps, and the FAQ lists minimum RAM requirements:

- **n8n / Coolify** (automation, self-hosted PaaS): comfortable from **2 GB** → the $35.99 plan handles these
- **Ollama, AnythingLLM, LibreChat, Hermes Agent**: at least **4 GB** → $59.99 plan
- **OpenClaw**: at least **8 GB** → $119.99 plan

That 4GB threshold is the real decision line for a lot of readers right now. Self-hosting an LLM chat frontend or running Ollama is one of the most common reasons people go looking for a cheap VPS, and plenty of budget providers' entry plans can't touch it — the $5/month tiers at most mainstream clouds top out at 1GB of RAM. If local AI tooling is your goal, the 4GB plan is the entry ticket: 👉 [check the 4GB plan's current price](https://my.racknerd.com/aff.php?aff=11397&pid=954)

For everything else, be honest with yourself about scale. A WordPress blog with light traffic, a monitoring stack, a few Docker containers, a game server for friends — the 2GB plan covers these. The 6GB and 8GB plans make sense for multi-site hosting or heavier workloads; if you're not sure you need them, you probably don't yet, and upgrading later is possible from the ctrl panel.

## The fine print: what you give up at this price

A cheap VPS this cheap is unmanaged, and the trade-offs are specific. Worth knowing before ordering rather than after:

- **Unmanaged service.** RackNerd supports the platform 24/7 — network issues, hardware, the host node. Everything inside your server (configuration, security patches, software) is on you. If you want someone to fix your broken Nginx config, this isn't that kind of service.
- **No automatic backups.** The specials don't include managed backups. Set up your own scheduled backups and keep a copy off the server. This is the single most common regret among budget-VPS users, and it takes ten minutes to prevent.
- **No managed firewall, DDoS mitigation, or DNS hosting** bundled in. You do get the ctrl Network Firewall for inbound traffic filtering, with rules you manage yourself from the panel, which covers a lot of basic use cases.
- **English-language support via tickets**, 24/7. Chinese-language hosting guides note there's no Chinese-speaking support staff, so factor that in if that matters to you. Payment-wise, PayPal and cards work; those same guides also report Alipay support, which makes checkout easier for many Asian buyers.
- **One IPv4 per plan.** If you ever need additional IPv4 addresses, confirm availability and pricing with a support ticket before assuming they exist on this plan line.

None of this is hidden — it's just rarely spelled out in comparison articles that rank for "cheap vps." If any of these are dealbreakers, you're better off paying more for a managed host than discovering them mid-incident.

## The holiday-promo wrinkle: cheaper, but with strings

Beyond the standard lineup above, RackNerd periodically runs time-limited promotions — Black Friday, New Year, and occasional flash sales — where the same resource tiers drop well below the regular specials. Past New Year promotions have listed a 1-core/1GB plan at around **$11.29/year** and a 1-core/2GB plan at $18.29/year, per third-party deal trackers that follow these sales.

Three things to know before you wait for one:

1. **Stock is unpredictable.** Promo listings sell out, get restocked, or disappear entirely; there's no schedule you can rely on.
2. **Configs differ from the regular specials.** A promo 2GB plan might carry 40GB SSD and 3.5TB traffic instead of the standard 35GB/5TB — sometimes better value, sometimes not, depending on which resource you actually need.
3. **Location limits exist.** During past New Year sales, the 1GB promo tier could only deploy in regular datacenters, while 2GB and above could use the Asia-optimized Los Angeles node. If a specific location matters to you, check what's selectable on the order page before paying.

If you need a server this week, the regular specials are a fine deal at any time. If you're flexible and patient, watching for a promo round can nearly halve the first year's cost — and the renewal stays at that promo price too, which is the part most people miss.

## Datacenter choice: 20 locations, with one caveat for Asian users

RackNerd operates 20 datacenter locations across North America, Europe, and Asia:

- **US (12):** Los Angeles, San Jose, Seattle, Utah, Chicago, Dallas, New York, New Jersey, Atlanta, Tampa, Miami, Ashburn
- **Canada (2):** Montreal, Toronto
- **Europe (5):** London, Amsterdam, Strasbourg, Frankfurt, Dublin
- **Asia (1):** Singapore

The one caveat: Asia is covered by a single location. Community guides commonly recommend the **Los Angeles DC-02** node for Asia-bound routes (it's the most in-demand location and goes out of stock periodically), and available datacenters are shown in real time on the order page, so pick from what's actually listed when you order. For serving mostly European visitors, the East Coast nodes (Ashburn, New York) or Frankfurt/Amsterdam are the sensible picks. Just don't expect mainland-China-optimized premium routes at this price — that's a different product category entirely.

## How RackNerd stacks up against the other cheap names

Based on verified third-party data (Cybernews, August 2026, plus public billing documentation for Vultr), here's the landscape for entry-level plans:

| Provider | Entry price | Entry specs | Billing & renewal | Notes |
| --- | --- | --- | --- | --- |
| RackNerd | $1.83/mo (billed $21.99/yr) | 1 core / 1 GB / 20 GB SSD / 3 TB | Annual, renews at the same price | Unmanaged, root access, 20 locations |
| IONOS | $2.00/mo | 1 vCPU / 1 GB / 10 GB NVMe | Higher tiers jump on renewal (M: $4→$8) | 30-day refund, 99.99% uptime, backups cost extra |
| Vultr | $5.00/mo (regular, with IPv4) | 1 vCPU / 1 GB / 25 GB SSD / 1 TB | Hourly, capped at monthly rate; stopping ≠ stop billing | Fine-grained billing; APAC overage fees are higher |
| Hostinger | $5.84/mo | 1 vCPU / 4 GB / 50 GB NVMe | Promo-dependent | 30-day refund, AI-assisted management |
| DigitalOcean | $4.00/mo | — | — | Developer-friendly tooling |

The honest read: IONOS and Hostinger are easier for beginners (better dashboards, managed conveniences, formal money-back guarantees). Vultr suits workloads that genuinely benefit from per-hour billing — short-lived test instances, bursty jobs — provided you remember that Destroy, not Stop, is what ends the charges. RackNerd wins on raw cost per resource and on not raising your rent after year one. If you've never touched a Linux terminal, the managed-leaning options will hurt less. If you're comfortable with SSH — and most people searching for a cheap KVM VPS are — the price gap is hard to argue with.

## FAQ

**Is the price really the same at renewal?**
Yes for the specials on the official page — they're advertised as lifetime recurring. This is the plan line to buy. Holiday promo rounds, when they appear, also renew at their promo price, so a low first-year cost there doesn't turn into a surprise later.

**Is there a money-back guarantee?**
RackNerd doesn't advertise a formal money-back window on its specials page the way IONOS or Hostinger do (both offer 30 days). If refund flexibility matters to you, ask via a support ticket before ordering rather than assuming.

**Can I install my own OS?**
You can choose CentOS, Rocky Linux, AlmaLinux, Fedora, Debian, or Ubuntu at order time. Custom ISO installs are available on request through a support ticket, and the HTML5 VNC console in ctrl lets you install from your own media later.

**Is this good for production websites?**
For a small business site or blog, yes, with two conditions: you (or whoever maintains the server) are comfortable with basic Linux administration, and you've set up your own backup routine. For mission-critical workloads where an hour of downtime costs real money, a managed host with an SLA is the better spend.

## Bottom line, by situation

- Learning Linux, running a bot or a personal project: **1GB, $21.99/year**, done.
- Hosting an actual website, n8n automations, or a handful of Docker services: **2GB, $35.99/year** — the plan most readers should stop at.
- Self-hosting Ollama, AnythingLLM, or LibreChat: **4GB, $59.99/year**, and don't bother with anything smaller for those apps.
- Multi-site hosting or heavy traffic: **6GB or 8GB**.
- Want managed support, backups, and a 30-day refund window built in: RackNerd will frustrate you; the budget managed options fit better.
- On a very tight budget and can wait: keep an eye out for the next Black Friday or New Year promo round, where 1–2GB tiers have dipped to roughly $11–18/year.

Two things to confirm on the order page before paying: your preferred datacenter is actually in stock (LA DC-02 sells out often), and you've got your backup plan ready for day one. If that all sounds fine, 👉 [grab the RackNerd annual plan that fits and lock in the renewal-same-price rate](https://bit.ly/RacKnerd) — at these prices, the year-one-and-every-year-after math is the whole point.
