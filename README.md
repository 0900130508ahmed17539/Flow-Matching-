# Flow Matching for Controlled Image Generation

**Author:** Ahmed Mohammed Ahmed  
**Supervisor:** Dr Shane Josias  
**Institution:** Stellenbosch University  
**Degree:** Master of Science in Machine Learning and Artificial Intelligence  
**Date:** December 2025

---

## Abstract

Continuous normalizing flows trained through flow matching have achieved state-of-the-art results in generative modelling. However, it remains unclear how guidance mechanisms originally developed for diffusion models perform when adapted for flow matching. These mechanisms provide controllable generation by learning conditional distributions and offer flexible control over the trade-off between sample fidelity and diversity.

This work investigates how different conditioning strategies can be incorporated into flow matching to balance this trade-off. Three approaches are investigated: direct label conditioning, classifier guidance, and classifier-free guidance. Each is evaluated across three datasets in order of increasing complexity—MNIST, SVHN, and CIFAR-10—to assess its influence on sample quality and diversity.

The study finds that direct label conditioning enhances sample quality relative to an unconditional model, with the largest gains observed on simpler datasets, MNIST and SVHN, though it does not provide a mechanism for controlling the quality–diversity trade-off. Classifier guidance does not yield any improvement in sample quality compared to label conditioning, possibly because training the classifier on noisy interpolations is difficult. Classifier guidance additionally exhibits behaviour contrary to diffusion models: sample quality and diversity decline as guidance strength increases. Another interesting difference to the diffusion model literature is that optimal guidance scales are much lower for flow models. In contrast, classifier-free guidance showed the expected quality-diversity tradeoff across all datasets. As guidance strength increased, sample quality improved while diversity decreased. Its success may be due to joint training on the generative process itself, rather than reliance on an external classifier, which can be difficult to train. These findings suggest that classifier-free guidance provides the most reliable conditioning mechanism for flow matching.
