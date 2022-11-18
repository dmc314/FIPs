#  Revisiting a Sector Duration Multiplier Post Shark (nv17) Upgrade

## Summary 
[FIP-0036](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0036.md) proposed cryptoeconomic changes to the Filecoin protocol, and was the subject of lively debate within the Filecoin community.  While this FIP was rejected for inclusion in the upcoming nv17 "Shark" network upgrade, many believe its overarching goals were directionally positive for the network. There have been renewed calls to revisit and arrive at consensus for a solution to the problem-space FIP-0036 sought to address, especially amidst an uncertain economic environment both within and external to the Filecoin Network. 

This discussion revisits the problem motivation, and provides a suggested path forward following FIP-0036's resolution, maintaining that the stability and long-term health of the Filecoin network continue to be of paramount importance. 

## Problem Motivation
Since FIP-0036's rejection in September 2022, the macroeconomic environment, as well as the health of the Filecoin network have continued to worsen.

FIP-0036 was introduced in July 2022 amidst an uncertain and bearish outlook both within the blockchain space and in the broader global economy. One of the intended goals of the FIP was to introduce economic incentives to provide the network with tools to weather macroeconomic uncertainty, through introducing rewards for Storage Provider's long-term commitment to the network. Since the FIP's introduction, the global macroeconomic environment has only worsened, and cryptocurrency has faced many compounding additional headwinds. Volatility continues within web3, and the duration of this industry downturn is unclear. Following, FIP-0036's rejection in September 2022, the crypto industry, and by extension the Filecoin economy has been weathering unexpected shocks and industry-defining black swan events. 

Within the Filecoin Network, the amount of hardware backing the network continues to shrink. Expirations and terminations have follow on effects for the stability of storage markets, as pledged collateral is unlocked and enters the network's circulating supply.
![Baseline Crossing](./Baseline.png)

**Since July 2022 when FIP-0036 was initially proposed, the network has lost approximately 1 EiB of storage capacity.** 

This trend continuing affects and harms both economic and network security and stability. These economic realities underscore the **time-sensitivity** of shipping protocol changes to harden the network amidst elevated volatility. The global situation continues to evolve rapidly. Hence, this FIP discussion heavily biases towards reducing scope, complexity, and minor disagreement in favor of implementing a change in the positive direction sooner. 

## Suggested Paths Forward 

FIP-0036 introduced a number of interconnected adjustments to the protocol, with some changes meeting more community disfavour than others. Based on community feedback from the FIP-0036 process, there is high likelihood that we as a community can find broad consensus and value in the following measures, which are a modified subset of those proposed in FIP-0036:

1.  **No Change** to the Target Lock Percentage
    - This was a main point of opposition for many participants previously. In the current proposal the target lock parameter stays at 30%. We can revisit what different values of this parameter could mean for the network in a separate discussion in the future.
2.  Linear Sector Duration Multiplier (SDM) with Slope of 1x 
    - See below for the proposed SDM which remains the same from the final iteration of FIP-0036 proposal
    ![SDM](./SDM_Function.jpeg)
    - Any slope too high results in a sense of disparity. Any slope too low does not sufficiently compensate for the risk that longer commitment takes on and does not provide sufficient benefits to the network itself.
    - Any other function besides linear results in more complexity without clear gains.
3. The final point of recommendation provides **two mutually exclusive options**.     
- **Option 3A.**  Policy only applies to **newly committed sectors**. 
    - This is a tradeoff. Initially, FIP authors recommended applying the same policy at sector extension to allow CC sectors to function as a sponge to soak up liquidity when they are extended, reducing circulating supply and initial pledge for other SPs.
    - Option 3A would not allow CC sector extensions to provide this liquidity-locking sponge, but would eliminate perceptions of unfairness between sectors with verified deals and sectors without such deals. 
    - Option 3A also mitigates many community concerns about treatment of existing sectors, deprioritizing mechanisms such as:
        - **Resnapping**: This is still important but applying policy Option 3A only to newly committed sectors reduces resnapping to an orthogonal concern. 
        - Linear Duration Multiplier can now start at 1-year instead of 540 days; there is no comparative disadvantage to sectors *already committed* for greater than 1-year, since this policy only applies to newly committed sectors. 
- **Option 3B.**  Policy applies at both sector upgrade and extension. 
    - This was the original policy proposed in the final iteration of FIP-0036 with the main tradeoff explained above in Option A. 








