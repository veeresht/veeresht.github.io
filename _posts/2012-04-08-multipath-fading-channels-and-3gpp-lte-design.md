---
layout: post
title: Multipath Fading Channels and 3GPP-LTE Design
date: 2012-04-08 15:00:00
description: Exploring parameter value choices in 3GPP-LTE design with respect to effects of multipath fading. 
tags: multipath-fading 3gpp-lte 
categories: communication-systems
featured: false
---

This article attempts to explain the rationale behind choosing particular parameter values in the design of the 3GPP-LTE standard using the concepts related to the effects of multipath fading channels in wireless communications.

Multipath fading channels are often defined by four key parameters in the theory of wireless communications. These are the Delay Spread ($$T_d$$) and the Coherence Bandwidth ($$W_c$$) defining the multipath characteristics of the wireless channel; the Doppler Spread ($$D_s$$) and the Coherence Time ($$T_c$$) defining the fading characteristics of the wireless channel. [1] presents an excellent treatment of these concepts.

The 3GPP-LTE standard specification [2] defines the system parameters for the OFDMA based physical layer downlink signal. Considering a system of bandwidth 10 MHz, other parameters defined are as follows:

Sampling Rate: 15.36 MHz  
FFT Size: 1024  
Sub-carrier Spacing: 15 KHz  
Normal mode CP Length: 72 (4.6875 $$\mu$$s)  
Duration of one OFDM symbol: ≈ 71.3541 $$\mu$$s  
Frequency domain spacing between reference symbol sub-carriers: 6 ($$\Delta W$$ = 0.09 MHz)  
Time domain spacing between reference OFDM symbols: 3 or 4; for this analysis, choose 4 ($$\Delta T$$ ≈ 285.42 $$\mu$$s)   

The 3GPP-LTE standard specification [3] defines multipath fading channel models to be used in the design and evaluation of an LTE system. For our analysis, let us choose the Extended Typical Urban model (ETU) which has the highest worst case delay spread of $$T_d = 5000 ns$$ among the models defined. The maximum doppler frequency for the ETU300Hz model is 300 Hz.

Therefore, the coherence bandwidth $$W_c$$ is given by [1] $$W_c = 12 T_d = 0.1$$MHz. Comparing this with $$\Delta W$$ as defined above, we have $$\Delta W < W_c$$, that is the spacing of the reference sub-carriers in the frequency domain is less than the coherence bandwidth of the channel and hence we can assume a flat fading channel characteristic for all the sub-carriers between the reference sub-carriers. This implies that the channel estimates obtained using the known reference sub-carriers can also be used for equalization of the other sub-carriers.

The ISI due to the multipath components of the channel is compensated by the cyclic prefix (CP) and we see that the the CP length in the normal mode (4.6875 $$\mu$$s) is slightly less than the worst case delay spread (5 $$\mu$$s). However LTE also supports an extended mode of CP where the length of the CP is 16.67 $$\mu$$s and this is sufficient to handle the worst case delay spread.

The doppler spread of the channel model is calculated from the maximum doppler frequency as $$ D_s = 300 Hz - (- 300 Hz) = 600 Hz$$.
Therefore, the coherence time $$T_c$$ is given by [1]

$$ T_c = \frac{1}{4 D_s} \approx 416.67 \mu s $$

Comparing this with $$\Delta T$$ as defined above, we have $$\Delta T < T_c$$, that is the spacing of the reference symbols in time domain is less than the coherence time of the channel and hence we can assume that the channel does not change during the time interval corresponding to $$\Delta T$$. This implies that the channel estimates obtained using the known reference symbols can also be used for equalization of the other non-reference OFDM symbols.

References

[1]. Tse, D and Viswanath, P. The wireless channel, In: Fundamentals of Wireless Communication. Cambridge University Press, 2005, 10 - 48.

[2]. 3GPP TS 36.211. Evolved Universal Terrestrial Radio Access (E-UTRA); Physical channels and modulation.

[3]. 3GPP TS 36.101. Evolved Universal Terrestrial Radio Access (E-UTRA); User Equipment (UE) radio transmission and reception.