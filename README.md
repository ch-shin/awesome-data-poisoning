# Awesome Data Poisoning[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
A list of resources releated to data poisoning in machine learning.

Curation of papers is generally based on the recent publication in top AI conferences (NeurIPS, ICML, ICLR, AAAI, KDD, etc.) or the impactfulness on data poisoning. Please feel free to [pull requests](https://github.com/ch-shin/awesome-data-poisoning/pulls) or [open an issue](https://github.com/ch-shin/awesome-data-poisoning/issues) if you know awesome resources.


## Papers

### Attacks
- [**BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain**](https://arxiv.org/pdf/1708.06733.pdf), arxiv 2017
  - Tianyu Gu, Brendan Dolan-Gavitt, Siddharth Garg
- [**Targeted backdoor attacks on deep learning systems using data poisoning**](https://arxiv.org/pdf/1712.05526.pdf), arxiv 2017
  - Xinyun Chen, Chang Liu, Bo Li, Kimberly Lu, Dawn Song
- [**Trojaning attack on neural networks**](https://arxiv.org/pdf/1712.05526.pdf), NDSS 2018
  - Yingqi Liu, Shiqing Ma, Yousra Aafer, Wen-Chuan Lee, Juan Zhai, Weihang Wang, Xiangyu Zhang
- [**Label-consistent backdoor attacks**](https://arxiv.org/pdf/1912.02771.pdf), arxiv 2019
  - Alexander Turner, Dimitris Tsipras, Aleksander Madry
  - This paper suggested two kinds of new attack methods - mainly inserting "confusing" poisoned data into training set so that it is not easy to detect. How to make such examples? 1) GAN based latent space interpolation 2) Adversarial perturbations
- [**Invisible backdoor attacks on deep neural networks via steganography and regularization**](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9186317&casa_token=oIzySL0ff20AAAAA:J_sBK-x736EqoE8mGUNcDvT79YINxvpTRL6Gx_V98dH46quPMFThYeWCNmcPyupRfK5U4mZJ&tag=1), IEEE Transactions on Dependable and Secure Computing 2020
  - Shaofeng Li, Minhui Xue, Benjamin Zhao, Haojin Zhu, Xinpeng Zhang
- [**Backdooring and poisoning neural networks with image-scaling attacks**](https://arxiv.org/pdf/2003.08633.pdf), arxiv 2020
  - Erwin Quiring, Konrad Rieck
- [**MetaPoison: Practical General-purpose Clean-label Data Poisoning**](https://arxiv.org/pdf/2004.00225v2.pdf), NeurIPS 2020
  - W. Ronny Huang, Jonas Geiping, Liam Fowl, Gavin Taylor, Tom Goldstein
- [**How To Backdoor Federated Learning**](http://proceedings.mlr.press/v108/bagdasaryan20a/bagdasaryan20a.pdf), AISTATS 2020
  - Eugene Bagdasaryan, Andreas Veit, Yiqing Hua, Deborah Estrin, Vitaly Shmatikov

### Defenses
- [**Certified Defenses for Data Poisoning Attacks**](https://arxiv.org/pdf/1706.03691v2.pdf), NeurIPS 2017
  - Jacob Steinhardt, Pang Wei Koh, Percy Liang
- [**Spectral Signatures in Backdoor Attacks**](https://proceedings.neurips.cc/paper/2018/file/280cf18baf4311c92aa5a042336587d3-Paper.pdf), NeurIPS 2018
  - Brandon Tran, Jerry Li
  - Backdoor attacks generally have a higher value when projected on the top principal direction of representations --> Filter poisoned data based on them, + Some theoretical guarantees
- [**Using Trusted Data to Train Deep Networks on Labels Corrupted by Severe Noise**](https://arxiv.org/pdf/1802.05300.pdf), NeurIPS 2018
  - Dan Hendrycks, Mantas Mazeika, Duncan Wilson, Kevin Gimpel
- [**Poison Frogs! Targeted Clean-Label Poisoning Attacks on Neural Networks**](https://arxiv.org/pdf/1804.00792v2.pdf), NeurIPS 2018
  - Ali Shafahi, W. Ronny Huang, Mahyar Najibi, Octavian Suciu, Christoph Studer, Tudor Dumitras, Tom Goldstein
- [**Sever: A Robust Meta-Algorithm for Stochastic Optimization**](http://proceedings.mlr.press/v97/diakonikolas19a/diakonikolas19a.pdf), ICML 2019
  - Ilias Diakonikolas, Gautam Kamath, Daniel Kane, Jerry Li, Jacob Steinhardt, Alistair Stewart
  - Poisoned data generally have a higher score when projected on the top principal direction of *gradients* --> Filter poisoned data based on them, + Some theoretical guarante
- [**Learning with Bad Training Data via Iterative Trimmed Loss Minimization**](http://proceedings.mlr.press/v97/shen19e/shen19e.pdf), ICML 2019
  - Yanyao Shen, Sujay Sanghavi
  - Literally, trim some portion of examples that have large losses in each iteration. Theoretical guarantee on linear regression.
- [**Data Poisoning Attacks in Multi-Party Learning**](http://proceedings.mlr.press/v97/mahloujifar19a/mahloujifar19a.pdf), ICML 2019
  - Saeed Mahloujifar, Mohammad Mahmoody, Ameer Mohammed
- [**Transferable Clean-Label Poisoning Attacks on Deep Neural Nets**](https://arxiv.org/pdf/1905.05897.pdf), ICML 2019
  - Chen Zhu, W. Ronny Huang, Ali Shafahi, Hengduo Li, Gavin Taylor, Christoph Studer, Tom Goldstein
- [**The Curse of Concentration in Robust Learning: Evasion and Poisoning Attacks from Concentration of Measure**](https://arxiv.org/pdf/1809.03063.pdf), AAAI 2019
  - Saeed Mahloujifar, Dimitrios I. Diochnos, Mohammad Mahmoody
- [**Reflection backdoor: A natural backdoor attack on deep neural networks**](https://arxiv.org/abs/2007.02343) ECCV 2020
  - Yunfei Liu, Xingjun Ma, James Bailey, Feng Lu
- [**Radioactive data: tracing through training**](https://arxiv.org/pdf/2002.00937.pdf), ICML 2020
  - Alexandre Sablayrolles, Douze Matthijs, Cordelia Schmid, Herve Jegou
- [**SPECTRE: Defending Against Backdoor Attacks Using Robust Covariance Estimation**](https://homes.cs.washington.edu/~sewoong/backdoor.pdf)
  - Jonathan Hayase, Weihao Kong, Ragahv Somani, Sewoong Oh
  - m-way pixel attack can circumvent PCA defense (Tran et al, Neurips 2018). --> Estimate robust covariance matrix (+ robust mean if you want) of representations and whiten the representations with the estimated covariance + quantum entropy outlier score (its name is scary.) --> better. 

### Benchmark
- [**Just How Toxic is Data Poisoning? A Unified Benchmark for Backdoor and Data Poisoning Attacks**](https://arxiv.org/pdf/2006.12557.pdf) [code](https://github.com/aks2203/poisoning-benchmark) ICML 2021
  - Avi Schwarzschild, Micah Goldblum, Arjun Gupta, John P. Dickerson, Tom Goldstein



## License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Changho Shin](https://github.com/ch-shin) has waived all copyright and related or neighboring rights to this work.
