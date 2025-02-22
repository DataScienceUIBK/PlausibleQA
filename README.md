# PlausibleQA: A Large-Scale QA Dataset with Answer Plausibility Scores

![License](https://img.shields.io/badge/license-Apache_2.0-blue.svg)
![HuggingFace](https://img.shields.io/badge/HuggingFace-dataset-important)

<img src="https://raw.githubusercontent.com/DataScienceUIBK/PlausibleQA/main/Images/Pipeline.png">

**PlausibleQA** is a large-scale QA dataset designed to evaluate and enhance the ability of Large Language Models (LLMs) in distinguishing between correct and highly plausible incorrect answers. Unlike traditional QA datasets that primarily focus on correctness, PlausibleQA provides candidate answers annotated with plausibility scores and justifications.

- **10,000** questions
- **100,000** candidate answers with plausibility scores
- **1,000,000** justifications
- **Designed for MCQA and QA Robustness Assessment (QARA)**

## 📥 Dataset Download
The dataset is available on [Hugging Face](https://huggingface.co/datasets/JamshidJDMY/PlausibleQA):
```
wget "https://huggingface.co/datasets/JamshidJDMY/PlausibleQA/resolve/main/PlausibleQA.json?download=true"
```

## 📂 Repository Structure
```
│
├───Experiments
│   ├───MCQA
│   │       Gemma 2 9b.json
│   │       Gemma 2b.json
│   │       LLAMA 3.1 70b.json
│   │       LLAMA 3.1 8b.json
│   │       LLAMA 3.2 3b.json
│   │       Mistral 7b.json
│   │       Qwen 2.5 72b.json
│   │       Qwen 2.5 7b.json
│   │
│   └───Robustness
│           LLAMA 3.1 70b.json
│           LLAMA 3.1 8b.json
│           LLAMA 3.2 3b.json
│           Qwen 2.5 72b.json
│           Qwen 2.5 7b.json
│
└───HumanEvaluation
    ├───Person 1 - Person 6
    │       Evaluations (XLSX files per person)
```

## 🔬 Dataset Details
**Source:** The questions are sourced from three major QA datasets:
- **TriviaQA**
- **Natural Questions (NQ)**
- **WebQuestions (WebQ)**

Each question has **10 candidate answers** that are annotated with plausibility scores ranging from 0 to 100, along with justifications.

### ✨ Key Features
- **Plausibility-Aware MCQA**: Enables generating realistic distractors for multiple-choice question answering (MCQA).
- **Robustness Evaluation**: Measures model resilience against plausible yet incorrect answers.
- **Pairwise Answer Comparison**: Provides structured comparisons of candidate answers to refine plausibility assessments.
- **Human Evaluation**: 1,000,000 justifications validated by human annotators.

## 🛠 Usage
### Load the Dataset
```python
import json

with open("PlausibleQA.json", "r", encoding="utf-8") as f:
    data = json.load(f)

print(data[0])  # View first question
```

### Example Entry
```json
{
    "id": "Q1",
    "question": "What color is the live wire in an electric plug?",
    "correct_answer": "Brown",
    "candidate_answers": [
        { "answer": "Red", "plausibility_score": 96.17, "justification": "Red is associated with danger, which might be linked to a live wire." },
        { "answer": "Yellow", "plausibility_score": 53.41, "justification": "Yellow is used in electrical wiring, but not as commonly for live wires." },
        { "answer": "Purple", "plausibility_score": 14.96, "justification": "Purple is not commonly used for live wires." }
    ]
}
```

## 📊 Experiments & Evaluation
### MCQA Performance
LLMs were evaluated on multiple-choice question answering using **hard** and **easy** distractors from PlausibleQA. Results:

| Model             | Hard (w/ Answer) | Hard (wo/ Answer) | Easy (w/ Answer) | Easy (wo/ Answer) |
|------------------|----------------|-----------------|----------------|-----------------|
| LLaMA 3.1 70B   | **88.1%**       | 83.3%          | 72.0%          | 67.4%          |
| Qwen 2.5 72B    | 85.4%           | **83.3%**      | **75.6%**      | **71.2%**      |
| Mistral 7B      | 71.2%           | 63.2%          | 49.0%          | 39.5%          |
| LLaMA 3.2 3B    | 63.2%           | 58.5%          | 39.5%          | 29.0%          |
| Gemma 2B        | 13.8%           | 14.9%          | 9.4%           | 3.2%           |

### QA Robustness (QARA)
Models were tested on their ability to correctly reject plausible but incorrect answers.

| Model             | QARA Score (%) |
|------------------|--------------|
| LLaMA 3.1 70B   | **92.1%**    |
| Qwen 2.5 72B    | 91.7%        |
| LLaMA 3.2 3B    | 91.6%        |
| Qwen 2.5 7B     | 85.4%        |
| LLaMA 3.1 8B    | 84.5%        |

## 📜 Citation
If you use PlausibleQA, please cite our work:
```bibtex
@inproceedings{mozafari2025plausibleqa,
  title={Wrong Answers Can Also Be Useful: PlausibleQA - A Large-Scale QA Dataset with Answer Plausibility Scores},
  author={Mozafari, Jamshid and Abdallah, Abdelrahman and Piryani, Bhawna and Jatowt, Adam},
  booktitle={Proceedings of SIGIR '25},
  year={2025}
}
```

## 📧 Contact
For questions or contributions, reach out to:
- **Jamshid Mozafari** - jamshid.mozafari@uibk.ac.at
- **Abdelrahman Abdallah** - abdelrahman.abdallah@uibk.ac.at
- **Bhawna Piryani** - bhawna.piryani@uibk.ac.at
- **Adam Jatowt** - adam.jatowt@uibk.ac.at

## ⭐ Contribute
We welcome contributions! Feel free to open an issue or submit a pull request.

---
**PlausibleQA** is a resource to enhance QA research and robustness in LLMs. 🚀

