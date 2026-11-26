# 6wind vrouter License Pricing: What 10G to 100G Costs, Which Tier Your IPsec Tunnel Count Actually Requires, and What the $5 Trial Covers (Full Price Table)

A 6WIND vRouter license bought through SixtyNet starts at **$5** for a seven-day 10G trial and **$100 one time** for a perpetual 10G license covering 10 Gbps of throughput, 2,000 IPsec tunnels and 2 million CG-NAT conntracks. The top tier, unlimited throughput with unlimited tunnels, is **$4,500 one time**. There is no subscription and no renewal price on the listing, which is unusual enough in this category to be worth checking carefully before you commit.

Below is the full license table, the arithmetic behind the pricing, and the part most buyers get wrong: picking a tier by bandwidth when their IPsec tunnel count is what actually caps them.

> Most people evaluating 6wind vrouter should spend $5 on the seven-day 10G trial first, then buy the tier whose *tunnel* cap matches their real IPsec count. If you already know you need 10 Gbps and no more than 2,000 tunnels, the 10G perpetual license at $100 is the cheapest full license on the page.
>
> 👉 [See every 6WIND VSR license tier and its current price](https://sixtynet.net/aff.php?aff=39)

## All 6WIND VSR license tiers on the SixtyNet page

Each license is sold as software, and at checkout you choose whether it applies to **6WIND VSR** or **6WIND Virtual Accelerator**. Every paid tier is listed as perpetual licensing with free upgrades. Prices are "starting from" figures in USD, charged once.

| License tier | Max throughput | IPsec tunnels | CG-NAT conntracks | Price (one time) | Order |
| --- | --- | --- | --- | --- | --- |
| 6WIND 10G – 7 Day Trial | 10 Gbps | 2,000 | 2,000,000 | $5 | [Start the 7-day 10G trial](https://sixtynet.net/router?aff=39) |
| 6WIND 10G | 10 Gbps | 2,000 | 2,000,000 | $100 | [Order the 10G perpetual license](https://sixtynet.net/router?aff=39) |
| 6WIND 25G | 25 Gbps | 5,000 | 5,000,000 | $250 | [Order the 25G license](https://sixtynet.net/router?aff=39) |
| 6WIND 40G | 40 Gbps | 10,000 | 10,000,000 | $400 | [Order the 40G license](https://sixtynet.net/router?aff=39) |
| 6WIND 60G | 60 Gbps | 15,000 | 15,000,000 | $600 | [Order the 60G license](https://sixtynet.net/router?aff=39) |
| 6WIND 100G | 100 Gbps | 30,000 | 30,000,000 | $1,000 | [Order the 100G license](https://sixtynet.net/router?aff=39) |
| 6WIND Unlimited | Unlimited | Unlimited | Unlimited | $4,500 | [Order the unlimited license](https://sixtynet.net/router?aff=39) |

SixtyNet also sells VPS hosting and dedicated capacity on the same site. Those are separate products with their own hardware and monthly or annual billing, and none of them include a 6WIND license. If you arrived searching for 6wind vrouter, the table above is the only relevant product line.

## The pricing is exactly $10 per gigabit, which makes the choice easy

Divide price by throughput on the five capped tiers:

- 10G at $100 = $10.00 per Gbps
- 25G at $250 = $10.00 per Gbps
- 40G at $400 = $10.00 per Gbps
- 60G at $600 = $10.00 per Gbps
- 100G at $1,000 = $10.00 per Gbps

There is no volume discount for buying bigger, and no penalty for buying small. You are paying a flat rate per gigabit of licensed throughput, so the tier you pick should be the smallest one that clears your peak requirement. Buying up "to be safe" costs exactly what it would cost later.

The 40G tier is the one place where the maths changes in your favour. Tunnel density per gigabit rises from 200 on the 10G and 25G licenses to 250 on the 40G and 60G licenses, and 300 on the 100G license. Conntrack density moves the same way: 200,000 per Gbps at 10G and 25G, 250,000 at 40G and 60G, 300,000 at 100G. If you are near a tunnel boundary, stepping up one tier can buy more headroom per dollar than the raw throughput number suggests.

The Unlimited tier is the exception to the flat rate. At $4,500 it only beats the $10 per Gbps curve above roughly 450 Gbps of throughput, a scale almost nobody reading this operates at. It exists for buyers who need unlimited tunnels or conntracks rather than unlimited bandwidth.

## Size the license by IPsec tunnels, not by bandwidth

This is where the license caps bite. If you plan 3,000 site-to-site tunnels but only push 2 Gbps of traffic, the 10G license blocks you at 2,000 tunnels regardless of how much bandwidth you have left. The 25G license at $250 is your entry point.

A concrete example from 6WIND's own published demo configuration puts this in perspective. The company's VPN concentrator demo shows **10,000 tunnels sustaining 10 Gbps in both directions**. On SixtyNet's license caps, 10 Gbps alone would fit the $100 10G tier, but 10,000 tunnels push the same deployment into the **$400 40G tier**. Bandwidth-first sizing would have under-bought by two tiers.

Use this order when you size:

1. **Peak concurrent IPsec tunnels.** This is usually the binding constraint for VPN concentrator and site-to-site deployments.
2. **Peak CG-NAT conntracks**, if you are also terminating subscriber traffic. The caps scale with the tier, so a CGNAT-heavy deployment may need the higher tier for conntracks alone.
3. **Peak throughput in Gbps**, after the two above are satisfied.

## What the license includes, and what it does not

The license is for software that runs on hardware you supply. 6WIND's own product pages describe vRouter running in **bare metal and virtual machine configurations on commercial-off-the-shelf (COTS) servers**, with connectivity from **1G to multiple 100G**. A 2020 6WIND press release lists supported deployment targets for the vRouter family as bare metal on Intel Xeon and Atom servers, plus VMware ESXi, Linux KVM and AWS, with Intel, Mellanox and Broadcom NICs.

That list comes from 6WIND's Border Router announcement, not from the SixtyNet license page, so treat it as a starting point for a compatibility question rather than an answer. The SixtyNet listing does not state which hypervisors, CPU platforms or NIC models are validated for these specific licenses. Confirm that with the seller before you pay, especially if you are running on Arm or on a hypervisor outside the list above.

The listing also does not publish support terms, an SLA, licence transfer rules or a refund policy. What it does say, plainly, is **perpetual licensing** and **free upgrade** on every paid tier. That combination is the main commercial argument for this route: one payment, no annual renewal, and version upgrades included.

There is a $5 way to test all of this before you commit real money.

👉 [Try the 10G license for seven days before buying a perpetual tier](https://sixtynet.net/router?aff=39)

## Management and high availability: what to verify in a trial

The trial is worth spending on the operational questions, because these are the parts that decide whether the software fits your network rather than just your bandwidth bill.

**Automation depth.** 6WIND documents a CLI plus a NETCONF/YANG-based management engine built from a YANG datastore and a NETCONF server, supporting the standard configuration operations: `<get>`, `<get-config>`, `<edit-config>` and `<copy-config>`. That means full read and write configuration through NETCONF, not a read-only monitoring wrapper, which is the level you need for integration with an orchestrator or an existing management framework.

**Telemetry.** Monitoring is exposed as YANG-based KPIs that can be exported to a time-series database and an analytics dashboard. 6WIND's reference setup uses InfluxDB and Grafana. If your operations stack is Prometheus-based, plan for a translation layer.

**Failover.** VRRP provides a single IPsec endpoint in both directions, and IKE High Availability handles failover between nodes. Test an actual failover during the trial; HA behaviour under load is the thing that most often differs between a lab and production.

**Performance claims.** 6WIND's 2020 VPN concentrator page cites 18 Gbps of IPsec performance per processor core, scaling with core count; a 2019 page from the same company cites 18 Gbps per core plus 10.5 Gbps per secure VPN tunnel, described as a 50% gain over the previous generation. These are vendor figures from pages published between 2019 and 2020, not current independent benchmarks, and the hardware they were measured on is several generations old. Treat them as an indication of architecture, not a number to plan capacity around. Your licensed throughput cap is the hard limit anyway.

## Where this software fits: two deployment patterns

**Service provider VPN concentrator.** 6WIND's own case study describes AT&T using vRouter as the VPN concentrator behind its enterprise VPN service, vVIG (virtual VPN Internet Gateway), aggregating IPsec traffic from enterprise customers on COTS servers. The claimed results are a **70% CAPEX reduction**, support for all IPsec client types, and management of thousands of IPsec tunnels. That is a vendor-published customer story from 2020, not an independent audit, and it should be read as such. It does tell you the product has been deployed at Tier 1 scale for VPN aggregation.

**Multi-cloud border routing.** For service providers connecting customers to AWS, Azure and Google Cloud, 6WIND positions vRouter as a multi-cloud virtual border router that extends the security perimeter beyond the private cloud. Two numbers from that use case matter for sizing: **one vRouter instance can handle more than 100 customers** with high performance requirements, and customer separation is handled through **VRF**. If you are building a multi-tenant edge, 100-plus tenants per instance tells you roughly how many licenses you need at the start.

## How the reseller price compares with 6WIND's own list price

6WIND's February 2020 press release quoted an MSRP of **$2,950** (or €2,750) for a 10G perpetual license with Border Router options on its Turbo Router product. SixtyNet's 10G license is $100.

These are not the same SKU. The press release figure covers Turbo Router with border routing options; the SixtyNet listing sells 6WIND VSR or Virtual Accelerator licenses. Do not read the difference as a 97% discount, because it is not one. What the comparison does show is the order of magnitude 6WIND charges for direct licensing, which is why a reseller listing at $100 for a 10G perpetual license is worth a careful look rather than an assumption that something is wrong with it.

## Before you order

- **Write down three numbers**: peak IPsec tunnels, peak CG-NAT conntracks, peak Gbps. Match them against the table, not against the marketing throughput figure.
- **Decide VSR or Virtual Accelerator.** The license lets you pick either at purchase. If you are buying for DPDK-based acceleration rather than routing, say so before checkout.
- **Ask about platform support.** Hypervisor, CPU architecture and NIC validation are not published on the license page.
- **Check the payment method.** A third-party review of SixtyNet's VPS line reports that credit card payments were suspended at one point for fraud prevention and that the money-back window was three days rather than thirty. That review covers VPS products, not licenses, and the license page states no refund terms at all. Confirm both points with the seller before paying, and use the $5 trial as your real safety net.
- **Do not buy Unlimited** unless you genuinely need unlimited tunnels or conntracks. Below roughly 450 Gbps, the capped tiers are cheaper for identical throughput.

The decision rule, in one place: testing or unsure → $5 seven-day 10G trial. Up to 2,000 tunnels and 10 Gbps → $100. Up to 5,000 tunnels → $250. Up to 10,000 tunnels → $400. Up to 15,000 → $600. Up to 30,000 → $1,000. Beyond that, or unlimited tunnels and conntracks → $4,500.

👉 [Compare all seven 6WIND license tiers and order the one that matches your tunnel count](https://sixtynet.net/aff.php?aff=39)
