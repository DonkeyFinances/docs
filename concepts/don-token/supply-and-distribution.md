---
description: CRV Supply and Distribution
---

# Supply & Distribution

There is a **fixed total supply of 3,030,303,031 CRV**. No CRV tokens can ever be minted after that. The total supply of CRV tokens allocated to different groups is shown below in the "CRV Total Allocation" chart. **Not all CRV are currently minted or circulating**. CRV tokens are slowly minted to the community each week and will continue to be released for over 200 years. The amount of tokens minted each week is defined in the [community emissions section](https://resources.curve.fi/crv-token/supply-distribution/#community-emissions-crv-inflation).

Have a look over this page to learn about how CRV has been allocated and how much is distributed each week. The [Supply Calculator](https://resources.curve.fi/crv-token/supply-distribution/#supply-calculator) is a great tool see the CRV supply and statistics on any date.

#### **Total Supply Allocation** <a href="#total-supply-allocation" id="total-supply-allocation"></a>

The below chart shows the total allocation of CRV to different groups within the Curve ecosystem.



Add graph



The above allocation shows that the **community will own 67% of all CRV** when the total supply is distributed, but note that **CRV tokens will continue to be distributed until 2376**, but meaningful distributions will stop in around 50 years, see [notable emissions years](https://resources.curve.fi/crv-token/supply-distribution/#notable-emission-years) for how the yearly distribution will change over time.

***

#### **Token Launch** <a href="#token-launch" id="token-launch"></a>

CRV officially launched on the **13th of August 2020**. At the time of launch there were no unlocked tokens. **All** tokens in the launch were linearly vested for 1-4 years (gradually unlocking over a period of 1-4 years). The initial supply is quoted as 1,303,030,303 because these tokens were pre-mined and sent into the vesting contracts, which gradually unlocked them. Below shows the allocation to different groups of the initial distribution.



The circulating supply was 0 at launch. Each day of the first year approx. 750k tokens were emitted to the community for providing liquidity and 1.65million tokens were vested (unlocked). Use the [supply calculator below](https://resources.curve.fi/crv-token/supply-distribution/#supply-calculator) to see how quickly tokens became liquid and circulating.

Tip

6 year CRV release schedule is available here: [https://dao.curve.fi/releaseschedule](https://dao.curve.fi/releaseschedule), or the full release schedule is available as a google spreadsheet [here](https://docs.google.com/spreadsheets/d/1kFFdaLCX8ISM7yzvfUmuz151QiRzrFfaljCzEiO6sus/edit?usp=sharing).

***

#### **Community Emissions (CRV Inflation)**[¶](https://resources.curve.fi/crv-token/supply-distribution/#community-emissions-crv-inflation) <a href="#community-emissions-crv-inflation" id="community-emissions-crv-inflation"></a>

Community emissions (regularly called CRV Inflation) are minted and allocated to gauges based on the weekly weight gauge vote. Gauges have a very flexible design and can direct emissions to liquidity pools and suppliers of a lending market, or even to funding for the Vyper programming language.

Community emissions reduce each year. They are modelled off the Bitcoin Halving which halves the allocation every 4 years, in Curve however, we reduce rewards by 214 every 365 days instead. This works out to be approx. 16% each year and 50% every 4 years. Community emissions were initially set at 274,815,283 CRV for the first year. This means the formula for how much CRV is emitted to the community in any year is:





Where `year` is the number of years after 13th August 2020, e.g., year 1 emissions are for the period 13th August 2021 until 13th August 2022. The emissions for year 10 are for the period of 11th August 2030 - 11th August 2031 (2 leap years with 366 days, yet Curve assumes all years have 365 days), this would come to 48,580,938 CRV emitted for that year.

In the smart contracts the yearly community emissions is not defined, it's actually defined as a rate of CRV emitted per second, we can convert between the yearly and per second value using the following formula:





We divide by 365×84600 because there is 365 days in a year and 86400 seconds in a day.

The emission rate has 18 decimal places, this means that **emissions continue for 245 years**. The emission rate will be 0.000000000000000001 CRV/sec in year 2265. **Emissions are hardcoded and cannot change**. See the [notable emission years](https://resources.curve.fi/crv-token/supply-distribution/#notable-emission-years) below, or have a play with the [supply calculator](https://resources.curve.fi/crv-token/supply-distribution/#supply-calculator) to see how much CRV will be distributed and to who in different years.

See [this section](https://resources.curve.fi/crv-token/faq/#how-does-the-yearly-emissions-reduction-work) of the FAQ for how the yearly reduction works. See [this section](https://resources.curve.fi/crv-token/faq/#how-is-crv-minted) for how CRV is minted and added to the supply.

**CRV Emissions for the next 10 years**[**¶**](https://resources.curve.fi/crv-token/supply-distribution/#crv-emissions-for-the-next-10-years)

See below for a chart of how the CRV will be distributed each year for the next 10 years. This year (2024), is the last year of the Core Team's CRV allocation vesting. After August 12th, 2024 all CRV added to the circulating supply will be distributed to the community through gauges, and CRV inflation will fall dramatically from 20.37% to 6.34% for the year.

_Note: dashed lines are percentage values and relate to the percentage axis, other lines relate to the CRV amount axis, click on datasets to turn them on/off._
