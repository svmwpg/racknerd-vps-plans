# RackNerd VPS deals: the five annual plans, which one your stack actually needs, and how renewal, refunds and one-click apps work

RackNerd's current VPS specials run from **$21.99 a year for 1 GB** up to **$119.99 a year for 8 GB**. All five are annual-only KVM plans with full root access, one IPv4 address and a 1Gbps port, and the rate you sign up at is the rate you renew at. For most self-hosted setups, a few Docker containers plus a small database, the **4 GB plan at $59.99 a year** is the one worth buying.

Below: the full price table, the RAM thresholds RackNerd publishes for its one-click apps, the real gap between monthly and annual billing, and the three clauses that decide whether this host fits you at all.

> **Quick pick:** 4 GB RAM, 3 vCPU, 60 GB SSD, 7 TB transfer, **$59.99/year**, renews at the same price. Clears the 4 GB minimum for AnythingLLM, Ollama and LibreChat, and leaves room for everything else.
> 👉 [Start the 4 GB KVM special at $59.99/year](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397)

## All five RackNerd VPS deals, side by side

| Plan | vCPU / RAM | SSD / monthly transfer | Price (USD/year) | Order |
| --- | --- | --- | --- | --- |
| 1 GB KVM VPS | 1 vCPU / 1 GB | 20 GB / 3 TB | $21.99 | [Order the 1 GB plan](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397) |
| 2 GB KVM VPS | 2 vCPU / 2 GB | 35 GB / 5 TB | $35.99 | [Order the 2 GB plan](https://my.racknerd.com/cart.php?a=add&pid=953&aff=11397) |
| 4 GB KVM VPS | 3 vCPU / 4 GB | 60 GB / 7 TB | $59.99 | [Order the 4 GB plan](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397) |
| 6 GB KVM VPS | 6 vCPU / 6 GB | 100 GB / 12 TB | $89.99 | [Order the 6 GB plan](https://my.racknerd.com/cart.php?a=add&pid=955&aff=11397) |
| 8 GB KVM VPS | 7 vCPU / 8 GB | 150 GB / 20 TB | $119.99 | [Order the 8 GB plan](https://my.racknerd.com/cart.php?a=add&pid=956&aff=11397) |

Every plan includes one IPv4 address, a 1Gbps network port, full root SSH access, the ctrl control panel, and provisioning right after payment clears. Your choice of CentOS, Rocky Linux, AlmaLinux, Fedora, Debian or Ubuntu at checkout; a custom ISO needs a support ticket.

Two notes on accuracy, because older listings get these wrong. The 4 GB tier is **3 vCPU cores** on RackNerd's own page, not the 2 vCores some affiliate sites still show. And the panel is **ctrl**, RackNerd's in-house panel, not SolusVM. Any deal page describing SolusVM is working from a stale spec sheet.

## How much RAM does your workload actually need?

RAM runs out before vCPU does on self-hosted stacks. A local model or a database-backed app will exhaust memory while the CPU sits at 15%. RackNerd publishes minimums for its one-click catalogue, which makes a decent buying rule even if you install everything by hand over SSH:

- **n8n, Coolify:** comfortable from **2 GB**. The $35.99 plan handles either one with a little headroom.
- **AnythingLLM, Ollama, LibreChat, Hermes Agent:** want at least **4 GB**. This is where the $59.99 plan earns its price.
- **OpenClaw:** wants at least **8 GB**. The $119.99 tier is the only special that clears it.
- **AdminBolt, CyberPanel, CloudPanel, Docker with Portainer:** no published floor, but a WordPress site with a database and a reverse proxy will be tight on 1 GB.

The 1 GB plan at $21.99 is a fine box for a proxy, a monitoring agent, a VPN endpoint or a bot that idles at 200 MB. It is not a web host. A single WordPress install with WooCommerce and Redis will swap, and you will blame the provider for a decision you made at checkout.

The 6 GB tier sits in an odd spot. If 4 GB is not enough, the reason is usually a model that wants 8 GB, so the $89.99 step tends to get skipped.

> 👉 [See the 8 GB special if you plan to run OpenClaw](https://my.racknerd.com/cart.php?a=add&pid=956&aff=11397)

## Monthly vs annual: the same specs cost about seven times more

These specials are annual-only. RackNerd runs a separate standard KVM catalogue with monthly billing, and it is priced nothing like the specials. A 2 GB monthly plan in the standard catalogue is listed at **$20.59/month**, roughly **$247 a year**, against **$35.99 a year** for the 2 GB special. The monthly version throws in a bit more storage and an extra vCPU. That does not come close to covering a 7x difference.

Treat the two as different products rather than a discount and its list price. The special is cheap because you prepay a year and accept a fixed configuration; the monthly plan is expensive because you can leave whenever you want.

That flexibility has a use. RackNerd does not offer refunds by default, so the company's own suggested workflow is to start monthly, confirm the route and the load, then move to an annual special once you are satisfied. A 1 GB monthly plan is listed around $17.99/month in third-party write-ups of the standard catalogue, which is an expensive month but a cheap mistake compared with a year you cannot cancel.

> 👉 [Compare the annual specials before you commit to a year](https://bit.ly/RacKnerd)

## Renewal, refunds, and the clauses nobody puts in a deals post

**Renewal is flat.** RackNerd's FAQ states it plainly: *"These RackNerd VPS specials are lifetime recurring. You can renew at the same rate for as long as you decide to keep the service."* No intro rate that doubles in year two. The catch is structural, not hidden: the price is tied to annual prepayment, and the monthly catalogue costs far more.

**There is no money-back guarantee.** From the terms: *"Refunds are issued on a case-by-case basis since by default no refunds are provided once payment is received."* In practice, a refund is plausible in the first minutes after delivery if the VPS will not boot or the IP is unreachable. It is not a 30-day window, and prepaid account credit does not come back. If a no-questions-asked trial period is a requirement, this host fails that requirement.

**Nested virtualization needs written permission.** Running VMs, a hypervisor, or a VPS resale platform inside a RackNerd KVM VPS requires written approval, and the VT-x/AMD-V flags are not guaranteed to be exposed. Container workloads are explicitly allowed: Docker, Docker Compose, LXC/LXD, Kubernetes, K3s all fine. Crypto mining including CPU mining, outbound DDoS, spam and brute-force traffic are banned platform-wide.

One more small thing: VPS orders do not need a coupon. The specials are already the discounted price, and a code typed at checkout mostly adds a support ticket to your first week.

## What ctrl actually does, and why unmanaged is the right word

ctrl is included with every special, and it covers the day-to-day work: power on and off, OS reinstall, an out-of-band HTML5 VNC console, root password reset, inbound firewall rules, plan upgrades, and the one-click app catalogue. There is a public interactive demo you can poke at without an account if you want to see the interface before paying.

The one-click list covers AdminBolt, OpenClaw, AnythingLLM, Ollama, LibreChat, n8n, Coolify, Hermes Agent, Docker with Portainer, CyberPanel and CloudPanel. When an install finishes, the credentials appear inside the panel. Anything not on the list installs over SSH like it would on any other box, because you keep full root.

Upgrades move you one tier up with a reboot and roughly a minute of downtime. The server is not rebuilt, and ctrl handles the move.

A RackNerd VPS special is **unmanaged**. You get root and a panel, not a sysadmin. Support covers the platform, and tickets run around the clock. Third-party write-ups and community posts consistently describe first responses in minutes to an hour, and one Trustpilot reviewer mentions a PTR/rDNS change handled in about 10 minutes. Those are individual reports, not a published SLA.

Locations: multiple datacenters across North America, Europe and Asia, with third-party counts putting it around 20. Pick the one closest to your users at checkout. RackNerd's FAQ and third-party listings note up to 100 free IPv6 addresses in Los Angeles and France, requested by ticket after ordering, with more locations promised.

> 👉 [Open a 2 GB special if you only need Docker and n8n](https://my.racknerd.com/cart.php?a=add&pid=953&aff=11397)

## Where RackNerd sits against the alternatives

| Provider | What you get that RackNerd does not | What it costs you |
| --- | --- | --- |
| Hostinger | Double the RAM at a comparable tier, NVMe, weekly backups, a polished panel with an AI assistant, and a real 30-day refund window | The KVM 2 plan runs roughly **$390 over two years** once the renewal is included, against about **$120** for two years of RackNerd's 4 GB special |
| Hetzner | Dedicated, not shared, vCPUs | Weaker fit if your users are in Asia or the Americas |
| Contabo | More RAM per dollar on monthly billing | Annual prepay is where RackNerd wins |
| DigitalOcean | The best documentation and a large one-click marketplace | The most expensive of the four |

The honest summary: RackNerd wins on long-term cost per gigabyte, because the rate never renews upward. It loses on refunds, on managed support, and on panel polish. If you need a 30-day no-questions refund, weekly backups or somebody else to administer the box, budget for Hostinger or a managed host instead. Paying $59.99 for a year you cannot cancel is worse than paying $390 for two years you can walk away from.

## The fall giveaway runs through November 30

Separate from the plan pricing, RackNerd is running a giveaway with LowEndBox that closes **November 30, 2026**. Prizes include a Meta Quest 3 512GB, a Synology DS225+ NAS, two Acer 27-inch monitors, ten $50 account credits, and **five 4 GB KVM VPS** with the first year free. Those five renew at $59.99/year with no obligation to continue.

To enter, message **@giveaway** on LowEndTalk with the word **PUMPKIN** and you get a secret code worth 100 bonus entries. The bonus code is only for accounts that were already 30 days old as of November 1, 2026; newer accounts can still enter the draw, just without the multiplier. No purchase is required.

This is a raffle, not a discount. PUMPKIN will not reduce the price of an order you place today, and it will not appear in any coupon field.

## What to buy, by situation

- **Proxy, bot, VPN endpoint, uptime monitor:** 1 GB at **$21.99/year**. Buying anything larger wastes money on a box that idles.
- **Docker stack, small database, a few sites behind a reverse proxy:** 4 GB at **$59.99/year**. This is the plan most readers should pick.
- **AnythingLLM, Ollama or LibreChat:** 4 GB minimum, so the same $59.99 plan, or 6 GB if you also run a database alongside the model.
- **OpenClaw or a pile of containers:** 8 GB at **$119.99/year**. Do not try to save the $60 by starting at 4 GB; the app will not run comfortably and an upgrade later costs more than buying right.
- **Nested virtualization or VPS resale:** none of the five. RackNerd's terms point you to a dedicated server for that.
- **You need a refund window or managed administration:** a different provider.

Two things to confirm at checkout: pick the datacenter nearest your users rather than the default, and make sure the cart shows annual billing. The specials only exist on the annual term, and the monthly catalogue is a different, much more expensive animal.

> 👉 [Pick your plan and datacenter from RackNerd's current specials](https://bit.ly/RacKnerd)
