# PyMC3: Implement Stochastic Gradient Hamiltonian Monte Carlo (SGHMC) Sampler 

## Abstract


## Technical Details

Bayesian approach offers an intuitive procedure for doing inference for statistical models. PyMC3 [?] provides a user-friendly framework for probabilistic programing (PP) in which Bayesian inference can be conducted. Central to this approach is the Bayes rule [?] which allows one to compute parameter posteriors for statistical models. However, closed form solutions exist only for the simplest of models and most real world examples require a sampling approach. The earliest approach for sampling, the Metropolis-Hastings algorithm [?], originates from physics-based models and has been judged one of the top ten algorithms of the 20th century [?]. 

Despite its initial success, the Metropolois-Hastings algorithm showed prohibitive convergence times, especially as the complexity of the models being implemented has increased. Innovations were again drawn from the realm of physics with the Hamiltonian Monte Carlo [?] (HMC) sampler. Briefly, the HMC sampler applies a deterministic proposal Metropolis method to the augmented target. In essence, this amounts to solving the equations of Hamiltonian dynamics which require the computation of a gradient of the _potential energy_ term. It is by taking advantage of this gradient, that the convergence properties can be considerably improved. The No U-Turn Sampler (NUTS) is an improvement over the HMC with self-tuning properties. Both HMC and NUTS approaches are implemented in PyMC3, which along with Stan [?] and R's LaplacesDemon package are the only PP packages to offer these samplers. 

However, the advantage of using the gradient information of the likelihood has also been diminished by the large volume of data being analysed. This is because the gradient now needs to be computed over a large space leading to expensive computations. Given the success of stochastic gradient approaches [?] in applications of big data analysis, it was considered that a noisy estimate of the gradient could be used instead of computing the exact gradient. This would alleviate the computational costs while maintaining favorable convergence properties. However, Chen et al. [?] showed that a naive implementation of a stochastic gradient would lead to loss of invariance property of HMC and thus erroneous conclusions. Instead, they suggest that one could apply a friction term to the Hamiltonian dynamics along with a stochastic gradient to recover the invariance property and thus obtain samples from the true target density. It is this sampling approach that we propose to implement as part of the google summer of code project. 

The SGHMC sampler will greatly enable PyMC3 to be scalable and also the application of bayesian models to machine learning problems. Indeed, the authors of the original paper [?] showed how such an approach would be advantageous in probabilistic matrix factorization problems. Similar approaches have also been used in Bayesian optimization [?] for the tuning of deep neural networks [?]. We strongly feel that in light of the advantages that SGHMC presents, its addition to the PyMC3 repertoire will provide a huge advantage to the science and technology community. 

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

{{ Future works }}

## Development Experience

{{ Development Experience }}

## Other Experiences

{{ Experience }}

## Why this project?

{{ Why you want to do this project? }}

## Appendix

{{ Extra content }}
