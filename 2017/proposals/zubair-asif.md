# PyMC3: Implement Stochastic Gradient Hamiltonian Monte Carlo (SGHMC) Sampler 

## Abstract
PyMC3 is one of the few libraries that offers gradient-based samplers for Bayesian inference. These samplers vastly improve convergence properties of the Markov chain and are indispensible when working with complex models. However, being gradient-based approaches they involve computation of a differential which when working in large parameter spaces can become computationally expensive. Recent literature has, thus, suggested use of a noisy estimate of the gradient which can alleviate some of this problem. Here, we propose to implment the startegy proposed by Chen *et al.* alongwith improvements due to Springenberg *et al.* However, because of the novelty of this approach, this project will require extensive experimentation on both example target distributions and real data sets, so that reliability of these samplers can be specified, while also providing a robust implementation. 

## Technical Details

Bayesian approach offers an intuitive procedure for doing inference for statistical models. PyMC3 [1] provides a user-friendly framework for probabilistic programing (PP) in which Bayesian inference can be conducted. Central to this approach is the Bayes rule [2] which allows one to compute parameter posteriors for statistical models. However, closed form solutions exist only for the simplest of models and most real world examples require a sampling approach. The earliest approach for sampling, the Metropolis-Hastings algorithm [3], originates from physics-based models and has been judged one of the top ten algorithms of the 20th century [4]. 

Despite its initial success, the Metropolois-Hastings algorithm showed prohibitive convergence times, especially as the complexity of the models being implemented has increased. Innovations were again drawn from the realm of physics with the Hamiltonian Monte Carlo [5] (HMC) sampler. Briefly, the HMC sampler applies a deterministic proposal Metropolis method to the augmented target. In essence, this amounts to solving the equations of Hamiltonian dynamics which require the computation of a gradient of the _potential energy_ term. It is by taking advantage of this gradient, that the convergence properties can be considerably improved. The No U-Turn Sampler (NUTS) is an improvement over the HMC with self-tuning properties. Both HMC and NUTS approaches are implemented in PyMC3, which along with Stan [6] and R's LaplacesDemon package are the only PP packages to offer these samplers. 

However, the advantage of using the gradient information of the likelihood has also been diminished by the large volume of data being analysed. This is because the gradient now needs to be computed over a large space leading to expensive computations. Given the success of stochastic gradient approaches [7] in applications of big data analysis, it was considered that a noisy estimate of the gradient could be used instead of computing the exact gradient. This would alleviate the computational costs while maintaining favorable convergence properties. However, Chen et al. [8] showed that a naive implementation of a stochastic gradient would lead to loss of invariance property of HMC and thus erroneous conclusions. Instead, they suggest that one could apply a friction term to the Hamiltonian dynamics along with a stochastic gradient to recover the invariance property and thus obtain samples from the true target density. It is this sampling approach that we propose to implement as part of the google summer of code project. 

The SGHMC sampler will greatly enable PyMC3 to be scalable and also the application of bayesian models to machine learning problems. Indeed, the authors of the original paper [8] showed how such an approach would be advantageous in probabilistic matrix factorization problems. Similar approaches have also been used in Bayesian optimization [9] for the tuning of deep neural networks [10]. We strongly feel that in light of the advantages that SGHMC presents, its addition to the PyMC3 repertoire will provide a huge advantage to the science and technology community. 

{{
Long description of the project.
**Must** include all technical details of the projects like libraries involved.
}}

## Schedule of Deliverables

### May 1th - May 28th, **Community Bonding Period**

{{ Delieverables }}

### May 29th - June 3rd

{{ Delieverables }}

### June 5th - June 9th

{{ Delieverables }}

### June 12th - June 16th

{{ Delieverables }}

### June 19th - June 23th, **End of Phase 1**

{{ Delieverables }}

### June 26 - June 30th, **Begin of Phase 2**

{{ Delieverables }}

### July 3rd - July 7th

{{ Delieverables }}

### July 10th - July 14th

{{ Delieverables }}

### July 17th - July 21th, **End of Phase 2**

{{ Delieverables }}

### July 24th - July 28th, **Begin of Phase 3**

{{ Delieverables }}

### July 31st - August 4th

{{ Delieverables }}

### August 7th - August 11th

{{ Delieverables }}

### August 14th - August 18th

{{ Delieverables }}

### August 21st - August 25th, **Final Week**

{{ Delieverables }}

### August 28th - August 29th, **Submit final work**

## Future works

I want to continue contributing to PyMC3 even after the completion of this project. Another project that I am passionate about is the implementation of ordinary differential equation (ODE) solves in PyMC3. Applicaiton areas like systems biology and pharmacokinetics would greatly benefit from having such solvers in the PyMC3 and it will aid in adoption of Bayesian methods by these communities also. 

In addition, I would like to popularise PyMC3 in my department and aim to hold a tutorial on Bayesian appproaches, particularly their implementations in PyMC3, at the conclusion of the summer. 

## Development Experience

{{ Development Experience }}

## Academic Experience

I am a graduate student in Computational Biology at the University of Southern California and also pursuing a Data Science masters in the Computer Science department. I have had the pleasure to work through extensive Bayesian literature, especially as it relates to systems biology and genetics. I have also worked on several Machine Learning projects, either individually or collectively in teams. 

## Why this project?

My current research interests have involved the use of Bayesian methods for inference problems in systems biology and spatial demography. I have used existing MCMC samplers and self-written implementations. I feel that a contribution to PyMC3 requires not only a good experience with development but also a good understanding of the methods. Experimentation and testing for MCMC methods can be a daunting, and I feel my experience with them can be helpful. In addition, while Hybrid Monte Carlo has been used extensively in physics, it is still woefully under-represented in biostatistics literature. I hope that my experience working PyMC3 will better my understanding of this and related approaches and help to popularize them in computational biology community. Most analysis in this community is still wedded to R implementations and researchers have regrettably not explored more robust implementations in python such as PyMC3. 

## Appendix

### References

- [1] Salvatier J, Wiecki TV, Fonnesbeck C. (2016) Probabilistic programming in Python using PyMC3. PeerJ Computer Science 2:e55 https://doi.org/10.7717/peerj-cs.55 .
- [2] Bayes T. (1763) An essay towards solving a Problem in the Doctrine of Chances. Philosophical Transactions of the Royal Society of London, 53: 370.
- [3] Hastings, WK. (1970) Monte Carlo sampling methods using markov chains and their applications. Biometrika, 57(1): 97-109.
- [4] Cipra BA. (2000) The Best of the 20th Century: Editors Name Top 10 Algorithms. SIAM News, 33(4).
- [5] Duane S, Kennedy AD, Pendleton BJ, Roweth D. (1987). Hybrid Monte Carlo. Physics Letters B. 195 (2): 216–222. https://doi.org/10.1016/0370-2693(87)91197-X .
- [6] Stan Development Team. (2015) Stan: a C++ library for probability and sampling . Available at http://mc-stan.org .
- [7] Robbins H, Monro S. (1951) A stochastic approximation method. The Annals of Mathematical Statistics, 22(3): 400–407.
- [8] Chen T, Fox EB, Guestrin C. (2014) Stochastic Gradient Hamiltonian Monte Carlo. In Proceedings of the 31st International Conference on Machine Learning. Beijing, China. JMLR: W&CP, 32.
- [9] Shahriari B, Swersky K, Wang Z, Adams RP, de Freitas N. (2015) Taking the Human Out of the Loop: A Review of Bayesian Optimization. Proceedings of the IEEE, 104(1): 148-175.
- [10] Springenberg JT, Klein A, Falkner S, Hutter F. (2016) Bayesian Optimization with Robust Bayesian Neural Networks. NIPS.
