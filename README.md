# us proxies: Buying US Residential IPs Without Overpaying — Plan Prices, State-Level Targeting, and Setup Explained

Most people typing "us proxies" into a search bar aren't browsing. They have a task that needs a United States IP address in the next hour — checking what a page looks like to an American visitor, keeping a US account session alive, pulling prices off a US storefront, or running a few hundred browser profiles that all need to look local. The search is a buying-intent search, and the useful answer is a price list, a targeting breakdown, and a straight answer about which billing model fits the job.

That's what this is. The provider in question is 9Proxy, a residential proxy network running since 2023, and the short version is that the US is one of its strongest pool segments — which matters more than any marketing line, because a US proxy is only as good as the number of clean US IPs sitting behind it.

## What "US proxies" usually means once you get specific

There are three different products hiding behind the same phrase, and they behave nothing alike.

**US residential proxies** route your traffic through real home internet connections in the United States. The IP belongs to an ISP like Comcast or Cox, so it looks like an ordinary person in a specific city. This is what 9Proxy sells. It's the option people mean when the target is a login page, a storefront, a social platform, or anything with a reputation check.

**US datacenter proxies** come from servers. Fast and cheap, but easy to spot, and usually blocked on the sites that made you look for proxies in the first place.

**US ISP / static residential** proxies sit in between: datacenter hardware registered to an ISP. Good for long-lived single accounts, less flexible for rotation.

9Proxy's catalog covers the first category in two billing shapes — pay per IP with unlimited bandwidth, or pay per GB of traffic — plus bundles that mix both. If your workload is "many profiles, not much data," the per-IP model is where the math gets interesting. If it's "one endpoint, lots of data," per-GB wins.

## Where a US IP actually changes the result

The difference between a US residential IP and, say, a German one is not cosmetic. Several categories of work simply don't return real data without it:

- **Ad verification.** Ad placements, creative rotation, and landing pages change by state and sometimes by city. Checking from a Dutch datacenter shows you a European ad stack, not the one your US campaign serves.
- **Price and stock checks.** Retailers, airlines, and ticketing platforms localize pricing and availability. A US zip-code-level IP is the only way to see the shelf a US buyer sees.
- **Multi-account work.** Social, marketplace, and advertising accounts are flagged when they log in from an IP in a country that doesn't match the account profile.
- **SERP and rank tracking.** Google results differ region by region. US-targeted queries need US IPs, ideally spread across states rather than hammering one subnet.
- **Authorized security testing and OSINT.** Reviewers who do this work tend to describe clean residential ranges as the baseline for testing how a target's protection layer treats ordinary visitor traffic versus known proxy ranges.

Streaming access is the one commonly assumed use case that deserves a caveat: residential proxies are not built for bandwidth-heavy unblocking, and at least one 2026 review notes 9Proxy can run into detection on streaming services even when it handles e-commerce and account tasks fine.

## How 9Proxy does US targeting

This is where US proxies stop being a commodity and start being a configuration question. 9Proxy lets you build targeting into the proxy username itself, which is unusual and very practical — no extra dashboard clicks, no separate endpoint per location.

The format looks like this:


<sub-user>-country-us-st-<state>-city-<city>-isp-<isp_code>-sst-<minutes>-ssid-<id>


A few real examples from the documentation:


subaccount-country-us                       # any US IP, rotates per request
subaccount-country-us-city-newyork          # rotating, New York only
subaccount-country-us-st-ohio               # Ohio only
subaccount-country-us-sst-15                # same US IP held for 15 minutes
subaccount-country-us-sst-15-ssid-id1       # parallel sticky session #1
subaccount-country-us-sst-15-ssid-id2       # parallel sticky session #2


Two things worth understanding before you buy.

Rotating mode gives you a fresh IP on every request. If you don't specify `sst` or `ssid`, that's what you get, and it's the right choice for scraping and price monitoring where continuity doesn't matter.

Sticky mode pins one IP for `sst` minutes. Add `ssid` and you can spin up multiple independent sticky IPs from the same configuration — which is how you keep twenty accounts separated without writing twenty configs.

One practical warning from the docs, and it's the mistake most people make in their first week: over-filtering kills your pool. Targeting `country` alone gives the widest selection and fastest response. Stacking state, city, and ISP narrows it fast. If your Ohio request suddenly gets slower, the problem is usually your filter, not the network.

For the per-IP model on desktop and Linux, filters cover country, state, city, ZIP code, and ISP. A single command — `9proxy proxy -c US -p 60000` — forwards a US residential IP to local port 60000, and one CLI flag re-uses an IP you already burned through in the last 24 hours, so you don't pay twice for the same address.

## The two billing models, and which one is cheaper for you

9Proxy doesn't hide this behind a single number, which is good, but it also means the wrong choice costs real money.

**Residential by IPs** charges for addresses, not traffic. Bandwidth is unlimited. An IP is only deducted when you actually forward it to a port, and unused IPs never expire — they sit in your balance until you need them. Once an address is live it stays up anywhere from a few hours to roughly 24 hours, which is normal for real home connections. When an IP dies, Auto Refresh Proxy swaps in a replacement, or Auto Rotation Proxy rotates on a schedule.

**Residential by GB** charges for traffic and gives you unlimited endpoint generation. Billing runs on purchased GB with 180-day validity (unlimited for enterprise accounts), rotating or sticky modes, and plain username/password or IP-whitelist authentication from the dashboard — no desktop app required.

The rough rule: if you're moving heavy, unpredictable data through a handful of sessions, per-IP is dramatically cheaper because bandwidth is free. If you need thousands of short-lived endpoints and each request is a few dozen kilobytes, per-GB is cheaper because you're not paying for addresses you'll never fully use.

## All current 9Proxy plans and prices

Prices below are the published rates in USD. Note the timing: 9Proxy announced its first price adjustment in three years, effective June 1, 2026, affecting IP-based and bundle packages. GB-based pricing was left untouched — if you're a bandwidth buyer, nothing changed.

**IP-based packages (unlimited bandwidth, IPs never expire, desktop app)**

| Package | Cost | Effective per IP | Buy |
| --- | --- | --- | --- |
| 100 IPs | $24 | $0.24 | [Start with the 100 IP package](https://bit.ly/9-Proxy) |
| 500 IPs | $72 | $0.144 | [Compare the 500 IP tier](https://bit.ly/9-Proxy) |
| 1,000 + 500 bonus IPs | $126 | $0.084 | [Grab the 1,500-IP entry tier](https://bit.ly/9-Proxy) |
| 2,500 IPs | $210 | $0.084 | [See the 2,500 IP package](https://bit.ly/9-Proxy) |
| 5,000 IPs | $360 | $0.072 | [Check the 5,000 IP plan](https://bit.ly/9-Proxy) |
| 15,000 IPs | $720 | $0.048 | [Buy the 15,000 IP package](https://bit.ly/9-Proxy) |
| 25,000 IPs | $863 | $0.035 | [Look at the 25,000 IP tier](https://bit.ly/9-Proxy) |
| 50,000 IPs | $1,438 | $0.029 | [Price out 50,000 IPs](https://bit.ly/9-Proxy) |

**Business IP packages (very high volume)**

| Package | Cost | Effective per IP | Buy |
| --- | --- | --- | --- |
| 100,000 IPs | $2,300 | $0.023 | [Request the 100k IP tier](https://bit.ly/9-Proxy) |
| 200,000 IPs | $4,140 | $0.021 | [See the 200k IP package](https://bit.ly/9-Proxy) |
| 500,000 IPs | $8,625 | $0.018 | [Talk to 9Proxy about 500k IPs](https://bit.ly/9-Proxy) |

**GB-based packages (unchanged after the June 2026 update, 180-day validity)**

| Package | Cost | Effective per GB | Buy |
| --- | --- | --- | --- |
| 5 GB | $15 | $3.00 | [Buy the 5 GB starter pack](https://bit.ly/9-Proxy) |
| 50 + 5 bonus GB | $105 | $2.10 | [Get the 55 GB pack](https://bit.ly/9-Proxy) |
| 100 GB | $150 | $1.50 | [Check the 100 GB package](https://bit.ly/9-Proxy) |
| 200 GB | $200 | $1.00 | [Buy 200 GB](https://bit.ly/9-Proxy) |
| 1,000 GB | $800 | $0.80 | [See the 1,000 GB tier](https://bit.ly/9-Proxy) |
| 2,000 GB | $1,500 | $0.75 | [Price the 2,000 GB package](https://bit.ly/9-Proxy) |
| 10,000 GB | — | $0.68 | [Ask about the highest GB tier](https://bit.ly/9-Proxy) |

Enterprise GB packages come with unlimited validity and custom pricing, which you'd need to request directly.

**Bundle packages (IPs + GB together, 180-day traffic validity)**

| Bundle | Contents | Price | Buy |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | [Compare the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 | [Take the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 | [Buy the Pro bundle](https://bit.ly/9-Proxy) |

For context on where these numbers sit: independent price tracking puts 9Proxy at the budget end of the residential market, with effective rates around $1.30–$2 per GB at standard volumes — roughly a seventh of mid-market providers charging $7–$8 per GB. Reviews also note the trade-off honestly: budget providers are fine on unprotected and moderately protected Tier 1–2 targets, and success rates drop on the hardest Tier 3 sites where premium networks still pull 98%+.

## How to sign up and buy

The account flow is short, but 9Proxy's affiliate system changes one detail: you can register with an invite code or through an invite link, and referrals get **5% off purchases**. That discount is documented on 9Proxy's own affiliate page, not a third-party rumor.

1. Open the sign-up page. Go straight there — password, or Google sign-in, plus an optional invite-code field.
2. Pick your model. Per-IP if you want unlimited bandwidth, per-GB if you want maximum endpoint flexibility.
3. Pay. Cards, bank cards, crypto (USDT, BTC, ETH, LTC, DOGE and others), Alipay, Apple Pay, Google Pay, or topped-up 9Proxy wallet balance.
4. Get access. Per-IP buyers download the desktop app for Windows, macOS, or Linux. Per-GB buyers can work entirely from the dashboard with username/password or IP whitelisting, or use Proxy2Web for browser-based work.

If you'd rather have the discount applied from the start, use the invite link when you create the account:

👉 [Create your 9Proxy account with the invite discount](https://bit.ly/9-Proxy)

## Which plan fits your US workload

**Testing the water, one browser, a handful of geo-checks.** The 5 GB pack at $15. It expires on the calendar, not on your patience, so it's fine for sporadic use.

**Ten to fifty browser profiles, social or marketplace accounts.** The 100 IP pack at $24, run in sticky mode with a distinct `ssid` per profile. Unused IPs don't expire, so this is genuinely low-risk for intermittent work.

**Agency or scraping operation with steady US traffic.** The 200 GB pack at $1,000-per-1,000-GB pricing (or specifically $200) is the sweet spot — $1.00/GB, and you're not rationing.

**Heavy, unpredictable bandwidth through a small number of sessions.** Per-IP, no question. 1,500 IPs for $126 with unlimited data is the reason this model exists.

**Reselling or running platform-scale automation.** The 50,000 IP and business tiers drop you to $0.018–$0.029 per IP, and 9Proxy publishes reseller pricing separately with discounts on large orders.

Two operational notes that reviewers consistently flag and that matter before you commit: the per-IP model requires the desktop app — the ClonBrowser setup guide and 9Proxy's own docs both describe local port forwarding as mandatory, which is clumsier than a browser extension for multi-device work. And there is no refund policy, because the product is non-refundable digital access. The compensation is a rule: report a dead IP within 60 seconds and a replacement lands on your balance immediately. That's why the "Today List" exists — a flagged-out IP reuses free within 24 hours rather than costing you a new one.

Free trials are promotional and availability-dependent, so don't plan your evaluation around getting one. Treat the $24 100-IP pack or the $15 GB pack as the real test — both are small enough that a failed experiment costs less than lunch.

## Setup, in the order you'll actually do it

1. Register and buy the package.
2. For per-IP: install the app, open the forwarding interface, press F to filter by country, state, city, ZIP, or ISP, then forward the IP to a port. It runs on `localhost:port`.
3. Verify before you build anything on top of it: `curl -x socks5://127.0.0.1:60000 https://ipinfo.io/json` and check that the returned IP is actually in the US.
4. For per-GB: skip the app. Build the username string with `country-us` plus whatever targeting you need, and point your tool at the host and port from your dashboard. SOCKS5 and HTTP/HTTPS both work, which covers anti-detect browsers, proxychains, and Python scripts without conversion hacks.

Hit a roadblock and it's a one-line fix — rename the target state, drop the ISP filter, add an `ssid` you forgot. Most first-day failures are configuration, not coverage.

## FAQ

**Is 9Proxy good for US-only work?** Coverage is strongest in the US, Southeast Asia, and Latin America, and the pool is 20M+ IPs across 90+ countries with city-level targeting and 99.95% uptime claimed by the vendor. US is not a weak spot here.

**Can I get US IPs in a specific state or city?** Yes — state, city, ZIP, and ISP filter levels are all documented, on both the per-IP app and the per-GB username string.

**Do US residential IPs stay the same forever?** No. Expect a few hours to about 24 hours per address on the per-IP model. That's the nature of residential networks, and it's why Auto Refresh and Auto Rotation exist.

**What happens if I buy and don't use it?** On per-IP, the IPs stay in your balance indefinitely. On per-GB, the traffic is valid for 180 days.

Write it down, pick your model, and buy from the link with the invite code attached — the 5% comes off automatically, and there's no reason to pay more for the same US IPs.

👉 [Get started with 9Proxy US proxies](https://bit.ly/9-Proxy)
