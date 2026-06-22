# General Project Planning

_Written by Mushthafa Sinuhaji_
_Created 2026-06-21_
_Last Updated 2026-06-22_

Keywords: neural network; multilayer perceptron; pareto optimisation; gradient descent; analog systems; digital systems

This project, titled "Comparing Equivalent MLPs in Analogue and Digital Hardware Through Cost-Driven Optimisation", is about analogue and digital hardwares in application to Machine Learning.

It follows, thereby, that we research a comparison between the two mediums and their effects on the 'costs' (temperature, time, electricity, and loss) produced by an identical model.

When we state 'equivalent MLPs', we refer to the intended architecture of the models in analogue and digital systems. Of course, reality will not fully reflect theory, as analogue systems are inherently stochastic; this study intends not to perfectly replicate the two systems and instead the differences in outcome between the two.

We will begin the project by defining the architecture to be replicated to both systems. It should be noted that Multilayer Perceptrons as well as deep learning in its simplest form (Fan et. Al, 2021, p.2) can be expressed as the following non-linear composition:

_{f(x; θ) = W_L σ_L-1 ( W_L-1 σ_L-2 ( ... W_2 σ_1 ( W_1 x ) ) ) }_

The custom MLP will follow this architecture without much alteration. For the purposes of this project, the MLP will be regress an approximation of an implied function based on a training dataset. Let any MLP be denoted as _f_. (We have yet to design the actual architecture.)

We notice that _f_ is simply a theoretical model which does not match empirical results; _f_ disregards stochasticisity, speed, and efficiency because it is an **abstraction** of how real behaviour should perform. We can denote the entire system hosting _f_ as _f~_, meaning that _f~_ is approximate to _f_ while also explicitly relying on the hardware parameters. This does not mean, however, that _f~_ is the empirical model, and is instead another theoretical model with larger context. We can define _f∘_ as the empirical model which portrays real results. (As seen later, we do not create one singular _f∘_ but instead multiple to compare. Same for _f~_!) Any formalisation of _f∘_ is approximately equal to _f~_ and will approximately simplify to _f_; they will not be equivalent.

This adaptation from _f_ to _f~_ serves several purposes, primarily being (1) that we create _f~_ in order to be able to derive costs pre-deployment (referring to thermal and electrical cost, as loss and training time are currently deterministically impossible to derive before deployment), and (2) we become able to compare theoretical results and costs (_f_ through _f~_) with empirical results through _f∘_. Quintessentially, _f_ and _f~_ are approximately equivalent, but _f~_ expands itself to rely on hardware parameters while _f_ simplifies such. 

More indepth, _f~_'s formal difference in comparison to _f_ is that it does not simplify the physical parameters of the hardware, such as material conductivity or resistance; additionally it does not explicitly define parameters θ. Instead, it denotes the structure of the physical system (with conductivity, resistance, etc.) from which θ emerges. Finally, the largest formal difference is that _f → ℝ_ while we design _f~ → ℝ^3_ into dimension 3 vector of heat, electricity, and loss (and, perhaps time). When we optimise _f_, we optimise the parameters θ, while in _f~_ we optimise hardware properties.

The hypothesis of this project will be a description of _f~_, as well as a derivation of heat and electrical use in both systems, as well as an estimation of loss and time.

The project will set the budget for each system to below $150 CAD. Informally put, I am broke. The total budget will be below $300 CAD, plus $100 CAD allowance.

Afterwards, the next steps will be physically deploying _f_ into an analog system(s), _f_analog_, and a digital system(s), _f_digital_. This will not guarantee an equivalence to _f_, but rather an approximation. This will also result in _f∘_analog_ and _f∘_digital_ as well as _f~_analog_ and _f~_digital_. (These functions will differ because the physical structure itself will be different, and we assume output will differ as well.) We will measure the temperature, electricity use, time, and lowest loss of backwards propagation, as well as the temperature, electricity use, and time of forwards propagation. 

Through pareto optimisation, we will find the optimal versions of both systems based on experimental data. We will also optimise for individual costs. We will map our findings to materials in the real world, and produce a final demonstration.

Finally, an important note is that this file is simply drafts of a plan. There are various concepts that must be formalised and made explicit, such as the definition of an equivalent system, and the way in which the analog and digital systems will be created without adding biases to one or the other (this applies mostly to structure because we are optimising the materials).
