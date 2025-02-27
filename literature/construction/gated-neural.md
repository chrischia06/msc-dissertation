# Rational Pricing

*Remark*: So-called 'rational pricing' is obtained by, which guarantees some no-arbitrage conditions for European Calls. Seems to be more of a CS based approach, usually evaluated on real S&P500 Options data from OptionMetrics.

**Yu Zheng Machine Learning Implied Option Information (2018)**
+ PHd Thesis. The relevant section for pricing is pg 48-69, which is the Gated Neural Networks for Option Pricing: Rationality by Design (2017) paper.

**Gated Neural Networks for Option Pricing: Rationality by Design (2017)**

+ https://www.pure.ed.ac.uk/ws/portalfiles/portal/29546775/yang_yu.pdf
+ https://github.com/arraystream/fftoptionlib
+ "for deep out-of-money options or those with long maturity, NN methods perform very badly (Bennell and Sutcliffe 2004)"
+ "(Gradojevic, Gencay, and Kukolj 2009) tried to address this issue by categorising options based on their moneyness and time to maturity, and training independent NNs for each class of options."
+ 6 no-arbitrage call constraints from Follmer, Schied, Stochastic Finance
+ Softplus * sigmoid $C(K/S, 1, T - t) = \sum_{j = 1}^{J}\sigma_{1}(b_{1, j} - me^{w_{1, j}})\sigma_{2}(b_{2, j}-\tau e^{w_{2, j}})e^{w_{3, j}}$, $J$ number of hidden units   
+ they verify asymptotics and no-arb conditions
+ Then $\sum_{i = 1}^{I} y_{i}(m, \tau)w_{i}(m, \tau)$ - $I$ number of single pricing models
+ Solution to no-arb bounds and asymptotics is to generate more edge examples
+ Gated Neural Network - Sigaud, O.; Masson, C.; Filliat, D.; and Stulp, F. 2015. Gated
networks: an inventory. CoRR abs/1512.03201
+ learn-ing from hints trick (Abu-Mostafa 1993)
+ can be calibrated to prices
+ The gated neural network satisfies some of the no-arbitrage constraints, in particular the right gradient signs
+ The multi-model is softmax + many gated models, sort of like an ensemble model
+ The gated and modular networks do not actually satisfy the intrinsic value bounds and exercise value equivalence at $\tau = 0$. The author's solution is to generate more data samples with $\tau = 0, K = 0$, sort of like importance sampling
+ Experiment Methodology: NNs are trained using last 5 days , calibration for BS / vol-models are done using the last day. Pricing error between real market prices and model prices for the next day are then evaluated under all models. *Remark*: This may be in effect equivalent to evaluating the explained PNL, or 1-day hedging error of the models, given that BS / vol-models would likely be used to recalibrate every trade as opposed to per day.
+ Single gated network has the worst results in the author's own experiment, but multi-model has the best. Suggests that ensembling is effective.
+ Slides: http://c4dm.eecs.qmul.ac.uk/horse2016/HORSE2016_Hospedales.pdf




**Option Pricing with Modular Neural Networks**

+ http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.87.3384&rep=rep1&type=pdf
+ Nikola Gradojevic, Ramazan Geņcay, Dragan Kukolj
+ the modular neural network seems to be similar to a gated neural network or ensemble methods


**A Hybrid Approach to Modular and Gated Neural Networks for Option Pricing and Hedging (2020)**
+ MSc Thesis
+ https://thesis.eur.nl/pub/53019/MSc_Thesis_Full.pdf


**Kaustubh Yada, Formulation Of A Rational Option Pricing Model using Artificial Neural Networks**

+ https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3724078
+ Student Paper
+ Fit NN on Heston, BS, and evaluate on real data


Generative Bayesian neural network model for risk-neutral pricing of American index options

+ Real market data

**Yi Cao, Xiaoquan, Liu Jia Zhai, Option valuation under no-arbitrage constraints with neural networks (2021)**	
+ https://www.sciencedirect.com/science/article/pii/S0377221720310134
+ 


Markus Ludwig, Robust Estimation of Shape-Constrained State Price Density Surfaces, (2015)

+ https://jod.pm-research.com/content/22/3/56.short

Gated Deep Neural Networks for Implied Volatility Surfaces
+ https://www.researchgate.net/profile/Bowei-Chen/publication/332778915_Incorporating_Prior_Financial_Domain_Knowledge_into_Neural_Networks_for_Implied_Volatility_Surface_Prediction/links/5d071c6792851c900442d698/Incorporating-Prior-Financial-Domain-Knowledge-into-Neural-Networks-for-Implied-Volatility-Surface-Prediction.pdf




https://github.com/koos808/Gated_Neural_Network_OptionPricing/blob/main/GNN_S%26P500.ipynb
https://github.com/sapphire921/NN-Option-Pricing
https://github.com/DovaX/artificial-neural-networks-in-option-pricing

https://github.com/DovaX/artificial-neural-networks-in-option-pricing/blob/master/Artifical%20Neural%20Networks%20in%20Option%20Pricing.pdf