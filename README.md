# **From Calibration Analysis to Hallucination Prediction: Investigating Uncertainty Dynamics in LLMs**

This project investigates the relationship between *predictive uncertainty* and *hallucination behavior* in Large Language Models (LLMs), with a particular focus on whether **token-level uncertainty dynamics** contain discriminative signals that are not captured by conventional confidence-based reliability metrics.

The study began with a calibration analysis of **GPT-4o** and **Gemini 3.5**, evaluating model reliability through metrics such as **Expected Calibration Error (ECE)**, **overconfidence gap**, **HCWR**, and **reliability diagrams**. Despite strong task performance, both models exhibited substantial *miscalibration* and *overconfidence*, motivating a deeper examination of uncertainty beyond response-level confidence estimates.

To analyze uncertainty at a finer granularity, **token-wise predictive entropy trajectories** were extracted throughout the autoregressive generation process. Multiple uncertainty-derived features were subsequently engineered, including **mean entropy**, **entropy variance**, **spike frequency**, **entropy jump magnitude**, and **entropy drift**. These features were evaluated on a human-annotated dataset of factual and hallucinated generations to assess their discriminative power.

Empirical results revealed that commonly used static uncertainty statistics provided little predictive value. Mean entropy, entropy variance, spike rate, and entropy jump magnitude all performed near chance level under stratified cross-validation. In contrast, **entropy drift**, defined as the difference between late-stage and early-stage predictive entropy, emerged as a strong discriminative signal, achieving a cross-validated **ROC-AUC** of approximately **0.80**.

A consistent uncertainty regime was observed across generations: factual responses tended to exhibit *positive entropy drift*, whereas hallucinated responses displayed *negative entropy drift*. This finding suggests that hallucinations are not necessarily characterized by elevated uncertainty magnitudes, but rather by distinct **temporal uncertainty dynamics** that unfold during generation.

Overall, the results indicate that uncertainty evolution contains substantially richer information than aggregate uncertainty statistics and highlight trajectory-based uncertainty modeling as a promising direction for **hallucination detection**, **reliability estimation**, **uncertainty quantification**, and **interpretability** research in modern LLMs.
