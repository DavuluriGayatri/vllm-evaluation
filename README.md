# Evaluating Security and Robustness of Vision-Language Models

## Project Overview

This project evaluates the safety, robustness, and performance of OpenAI’s GPT-4o and GPT-4o-mini vision-language models (VLMs) using the VLLM Safety Benchmark. The evaluation focuses on Out-of-Distribution (OOD) scenarios and complex visual challenges to identify the models' limitations and areas for improvement.

### Key Findings

- **Robustness:** GPT-4o demonstrated nearly 100% accuracy on standard datasets, while GPT-4o-mini showed approximately 90% accuracy.
- **Counterfactual Reasoning:** Both models faced challenges in reasoning with hypothetical scenarios, with accuracy dropping significantly for counterfactual questions.
- **Sketch Understanding:** GPT-4o outperformed GPT-4o-mini on sketch-based datasets but still struggled with ambiguous visuals.
- **Safety Concerns:** Both models displayed limitations in handling complex or adversarial scenarios, raising safety concerns for real-world applications.

---

## Project Details

### Datasets Used

- **OODCV-VQA Vision and Counterfactual**: Tests generalization and hypothetical reasoning.
- **Sketchy-VQA and Sketchy-VQA Challenging**: Assesses performance on abstract and ambiguous sketches.
- You can access the datasets [here](https://drive.google.com/file/d/11Xie17M_QRZ7g4nkMS03Lh4XR7I28hCY/view?usp=sharing)

### Methodology

1. **Dataset Preparation**: Organized datasets into tasks testing OOD generalization, counterfactual reasoning, and sketch understanding.
2. **API Integration**: Used OpenAI APIs to interact with GPT-4o and GPT-4o-mini.
3. **Evaluation Metrics**:
   - Accuracy: Exact matches to ground truth answers.
   - Semantic Similarity: Ensures alignment of meaning with ground truth.
4. **Qualitative Analysis**: Manual review of responses for deeper insights.

---

## Results Summary

| Dataset                  | GPT-4o Accuracy | GPT-4o-mini Accuracy |
| ------------------------ | --------------- | -------------------- |
| OODCV-VQA                | \~100%          | \~90%                |
| OODCV-VQA Counterfactual | Moderate        | Lower                |
| Sketchy-VQA              | High            | Moderate             |
| Sketchy-VQA Challenging  | Moderate        | Lower                |

### Observations

- **OOD Tasks:** GPT-4o’s robustness was evident in handling unfamiliar visual scenarios, but both models showed weaknesses in nuanced contexts.
- **Sketch Tasks:** GPT-4o consistently performed better than GPT-4o-mini, especially on ambiguous sketches.
- **Counterfactual Questions:** Highlighted the models' limitations in abstract and hypothetical reasoning.

---

## Conclusion

This project highlights the need for improved reasoning and safety mechanisms in VLMs. The findings emphasize the importance of:

- Enhanced training datasets for counterfactual and sketch reasoning.
- Robustness mechanisms to handle adversarial and ambiguous inputs.
- Comprehensive safety protocols for real-world applications.

---

## Repository Structure

- **`/notebooks/`**: Contains Jupyter notebooks for evaluation and analysis.
  - `vllm_eval_gpt-4o.ipynb`: Evaluation results for GPT-4o.
  - `vllm_eval_gpt-4o-mini.ipynb`: Evaluation results for GPT-4o-mini.
- **`/report/`**: Project report detailing methodology, results, and conclusions.
  - `vllm_safety_eval_report.pdf`: Full project report.

---

## How to Run the Code

1. Clone this repository:
   ```bash
   git clone https://github.com/DavuluriGayatri/vllm-evaluation.git
   cd vllm-evaluation
   ```
2. Open the Jupyter notebooks:
   ```bash
   notebooks
   ```
3. Execute the cells in the provided notebooks to reproduce the evaluation.

---

## Future Work

- Develop datasets to improve VLM reasoning in counterfactual and ambiguous scenarios.
- Explore adversarial training techniques to enhance robustness.
- Implement safety filters to mitigate risks in real-world deployments.

---

## References

- Tu, H. et al. (2023). “How many unicorns are in this image? A safety evaluation benchmark for vision LLMs”. arXiv:2311.16101.
- Patel, S. et al. (2023). “Evaluating Vision-Language Models’ Safety in Adversarial and Out-of-Distribution Scenarios”. ACL Proceedings.
- [Additional references available in `vllm_safety_eval_report.pdf`]

