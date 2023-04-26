# Empiric Methods
- very important research method
## Hypotheses Formulation
- two abstraction layers
	- **Empirical hypothesis**
		- content-related
		- textual description of what we expect
		- often not directly testable in experiments -> need to operationalise it
	- **Test hypothesis**
		- describe in a way applicalbe to a statistical test
		- $H_0$: null hypothesis describes opposite of empirical hypothesis
		- $H_1$: alternative hypohtesis describes actual empirical hypothesis
		- only when data suggest to reject $H_0$, we gain support for $H_1$
			- significance testing with p-value
- Errors
	- **Type-I Error**
		- false positive
	- **Type-II Error**
		- false negative

## Experiments
### Two different Experimental Approaches
#### Experiments with humans
- Comparison of methods/techniques/tools/processes
- Not directily repeatable, only (potentially) repicable
- Not completly autmatable
#### Experiments without humans
- Comparison of algroithms/implementations/systems
- Can be fully automated/repeatable

### Concepts involved in Experiments
![[ExperimentsConcepts.png|400]]
### Experiment Process
![[ExperimentProcess.png|400]]

### Analysis and Interpretation
- Descriptive statistics -> Data reduction -> Hypothesis testing -> Interpretation
#### Signifance Testing
- checks with which probability an empirically observed data should be expected in case the null hypothesis is true
- standardised result value is exceeding probability p
	- probability that a result from a sample takes place in case $H_0$ holds the population
	- if p-value below predefined (low) threshold -> *statistically significant* result

### Presentation and Package
- Publication
- Lab package
	- Data collection forms/tools/configurations
	- Analysis scripts
	- Experiment objects and data
- Company experience base
#### Report Structure
- Motivation
- Related Work
- Experimental design
- Execution
- Analysis
- Interpretation
- Conclusions and future work

## Experiments without humans
### Properties of Experiments 
- Reproducible
- Extensible
	- must allow comparison with past and future results
- Appicable
	- good relation to real world and considering specifics of real world
- Revisable
	- experiment results must help identify reasons if hypotheses are not met

### Four Experimental Methodologies
![[ExperimentalMethodologiesOverview.png|400]]
### Properties of Experiment Types
- When considering the properties and types of experiments, what properties are well supported by which methodologies?
#### In-Situ
- real application executed at real scale with real hardware
- when complex behaviour and interaction cannot be captured otherwise
- difficult to reproduce
#### Emulation
- real application but environment modelled
- provides synthetic experimental conditions
- virtualisation of hardware/other platform aspects
#### Benchmarking
- executing model/synthetic/generic applications in real environment
- goal to to quantitatively evaluate the environment such as hardware/operating system/middleware
#### Simulation
- executing model applications in modelled environment
- usually concentrates on specific part of environment
- most control of all experimental conditions and highly reproducible
- requires lot of modelling work -> effort-intense
- could abstract away problems that might be important in real setting

## Experiment Anti-Patterns
### Four Important Components of an Experiment
- Measurement Contexts
	- identify software/hardware components to vary/hold constant in experiment
- Workloads
	- identify benchmarks/application characterisics along with their inputs 
- Metrics
	- identify properties (how) to measure
- Data Analysis
	- identify how to analyse the data and interpret the results of the analysis to provide insight into resulting claims

![[OverviewExperimentalAnti-Patterns.png]]

#### Inappropriate Measurement Contexts
- when it's flawed or does not reflect the measurement context that is implicit in the claim
#### Ignored Measurement Contexts
- when experiment design does not consider measurement context when it is necessary to support claim
#### Inconsistent Measurement Contexts
- when an experiment compares two systems and uses different measurment contexts for each
- the more disparate the objects of comparison, the more difficult to ensure consistent measurement contexts
	- smallest difference in contexts can introduce bias and make results incomparable
	- maybe important to randomize experimental parameters
#### Irreproducible Measurement Contexts
- then the experiment is also irreproducible
- may be irreproducible because either not public or not documented

#### Inappropriate Workloads
- when it's flawed or does not reflect the workload that is implicit in the claim
#### Ignored Workloads
- in real world most systems are subjected to diverse workloads
- selection of workloads must include sufficient diversity to support intended claims
	- alternatively claim must be narrowed appropriately
#### Inconsistent Workloads
- when evalutation compares two or more systems, it's essential that they are subjected to same workloads
#### Irreproducible Workloads
- workloads used to evaluate innovation should include at least some workloads that others have access to
	- will enable others to reproduce results

#### Inappropriate Metrics
- when it's flawed or does not support the intended claims of experiment
- common manifestation it the use of a surrogate metric
	- easy to measure but may not correlate with desired metric it replaces
	- could be stated as a large threat to constructive validity
#### ingored Metrics
- when it's excluded depite being necessary to confirm evaluation claims
- two primary manifestations
	- ingnore cost of innovation while reporting only the benefit
	- report only ends-based/means-based merics
		- both important: ends-based often relevant to claim / means-based necessary for confirming the cause of the change in the ends-based one
#### Inconsistent Metrics
- to demonstrate superiority of innovation, many evaluations compare that innovation to an existing baseline
- if one metric in baseline used slightly different for innovation, metrics inconsistent and measurement results not necessarily comparable
#### Irreproducible Metrics
- metric's name may seem to unambiguously define the meaning of that metric
- often actual implementation of metric leaves lot of flexibility
- study needs to precisely define how metirc is measured -> otherwise future studies cannot produce comparable measurments

#### Inappropriate Data Analysis
- common goal is to draw conlusions about a population from a small subset of population -> sample
- for this generalisation to be valid, experiment must use appropriate analysis methods
#### Ignored Data Analysis
- Well-studied methods for analysing data are widely among experimental sciences
- using these methods reduces the risk of poor data analysis & interpretation
#### Inconsistent Data Analysis
- occurs when different data analysis techniques are applied to data pertaining to different objects of experimental study
#### Irreproducible Data Analysis
- to be reproducible, the experiment must carefully document the analysis it uses and identify & report any biases in the analysis
	- otherwise little hope of reproducing the analyses and arriving at same conclusion

## Artefact Evaluation
- artifact is any extraneous or confounding variable that can influence the results or conclusions of the experiment
- can be caused by a number of factors such as improper calibration, faulty equipment, incorrect measurement techniques, or incorrect assumptions
- some examples of common artifacts include measurement errors, background noise, and systematic bias
### Going Beyond Just Papers
- Criteria to check artefacts related to the paper:
	- **Consistent** with the paper. Does the artefact substantiate and help to reproduce the claims in the paper?
	- **Complete**. What is the fraction of the results that can be reproduced?
	- **Well documented.** Does the artefact descirbe and demonstrate how to apply the presented method to a new input?
	- **Easy to reuse.** How easy is it to reuse the provided artefact
- Articles with such associated evaluated artefacts enable a more comprehensive evaluation as well as strongly encourage replications.
- [ACM Artefact Review and Badging](https://www.acm.org/publications/policies/artifact-review-and-badging-current)
