|test| |codecov| |docs|

.. |test| image:: https://github.com/intsystems/ProjectTemplate/workflows/test/badge.svg
    :target: https://github.com/intsystems/ProjectTemplate/tree/master
    :alt: Test status
    
.. |codecov| image:: https://img.shields.io/codecov/c/github/intsystems/ProjectTemplate/master
    :target: https://app.codecov.io/gh/intsystems/ProjectTemplate
    :alt: Test coverage
    
.. |docs| image:: https://github.com/intsystems/ProjectTemplate/workflows/docs/badge.svg
    :target: https://intsystems.github.io/ProjectTemplate/
    :alt: Docs status


.. class:: center

    :Name of the task under study: Metric analysis of the parameter space of deep neural
networks
    :Author: Ruslan Rashidovich Nasyrov
    :Scientific supervisor: Ph.D., Strizhov Vadim Viktorovich


Abstract
========

The problem of dimensionality reduction in the parameter space of machine learning models
is being investigated. Regression and classification tasks are solved using fully connected
neural networks. A metric analysis of the parameter space of the model is conducted. It is
assumed that individual model parameters, random variables, are collected into vectors, which
are multidimensional random variables. The analysis of their mutual arrangement in space
represents the subject of investigation in this work. This analysis reduces the number of model
parameters, estimates their significance, and selects them. To determine the position of the
parameter vector in space, its mean and covariance matrix are estimated using bootstrap
methods, SGD estimation, and Bayesian neural networks. Experiments are conducted on tasks
of synthetic time series recovery, quasi-periodic accelerometer readings, and IRIS and MNIST
datasets.

`LinkReview <https://docs.google.com/document/d/197ZZ3pAftQzLtEjYcW8KKgALDledXuotjdYXJnXwgH0/edit?usp=sharing>`__,
`Paper <https://github.com/intsystems/2023-Project-141/blob/master/paper/Nasyrov2023_metric_analysis.pdf>`__,
`Slides <https://github.com/intsystems/2023-Project-141/blob/master/slides/Nasyrov2023Presentation.pdf>`__.

Software modules developed as part of the study
======================================================
1.The code of time series recovery experiments with SSA is `here <https://github.com/intsystems/2023-Project-141/blob/master/code/ssa_experiment.ipynb>`_.
2. The code of the experiments to restore the time series with 2NN is `here <https://github.com/intsystems/2023-Project-141/blob/master/code/2nn_experiment.ipynb>`_. 
	
Problem statment
======================================================
Problem 141
* __Title__: Metric analysis of deep network space parameters
* __Problem__: The structure of a neural work is exhaustive. The dimensionality of the parameter space should be reduced. The autoencoder in the subject of the investigation. Due to the continuous-time nature of the data, we analyze several types of autoencoders. We reconstruct spatial-time data, minimizing the error. 
* __Data__: 
	* Synthetic data sine for 2D visualizaion of the parameter distributions
	* Accelerometer quasiperiodic data
	* Limb movement quasiperiodic data (if any)
	* Video periodic data (cartoon, walking persona)
	* Video, fMRI, ECoG from the s41597-022-01173-0 
* __References__: 
	* [SSA and Hankel matrix construction](http://strijov.com/papers/Grabovoy2019QuasiPeriodicTimeSeries.pdf) or in [wiki](https://en.wikipedia.org/wiki/Singular_spectrum_analysis)
	* [Open multimodal iEEG-fMRI dataset from naturalistic stimulation](https://www.nature.com/articles/s41597-022-01173-0)
	* [Variational autoencoders to estimate parameters](https://arxiv.org/pdf/1606.05908.pdf)
	* RNN in the [5G book](https://arxiv.org/abs/2104.13478)
	* [Neural CDE](https://bit.ly/NeuroCDE)
* __Baseline__: RNN-like variational autoencoder in the criteria: error vs. complexity (number of parameters)
* __Roadmap__:
	* Prepare data so that the reconstruction work on a basic model (like SSA)
	* Estimate expectation and covariance of parameters (using VAE or else, to be discussed)
	* Reduce dimensionality, plot the error/complexity, plot the covariance
	* Run RNN-like model, plot
	* Assign the expectation and covariation matrix to each neuron of the model
	* Plot the parameter space regarding covariance as its metric tensor (end of minimum part)
	* Suggest a dimensionality reduction algorithm (naive part)
	* Run Neuro ODE/CDE model and plot the parameter space
	* Analyse the data distribution as the normalized flow 
	* Suggest the parameter space modification in terms of  the normalized flow (paradoxical part, diffusion model is needed)
	* Compare all models according to the criterion error/complexity (max part)
	* Construct the decoder model for any pair of data like fMRI-ECoG tensor and neuro CDE (supermax part)
* __Proposed solution__: description of the idea to implement in the project
* __Novelty__: Continous-time models are supposed to be simple due to their periodic nature. Since they approximate the vector fields, these models are universal. The model selection for the continuous time is not considered now, but at the time, it is acute for wearable multimedia devices for metaverse and augmented reality. 
* __Supergoal__ To join two encoders in a signal decoding model to reveal the connection between video and fMRI, between fMRI and ECoG.
* __Authors__: Expert Strijov, consultant ?

