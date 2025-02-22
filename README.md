# PlausibleQA: A Large-Scale QA Dataset with Answer Plausibility Scores

<a href="https://huggingface.co/datasets/JamshidJDMY/PlausibleQA/resolve/main/PlausibleQA.json?download=true"><img alt="Huggingface" src="https://img.shields.io/static/v1?label=Dataset&message=PlausibeQA&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAAAIGNIUk0AAHomAACAhAAA+gAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAIoUExURQAAAP/////57v/67xUVFf/clv+KAP/uzf/sxv8AAP9TAP/ltP///v/ouP/////////////////////////////8+v/pvP/biP/Vbf/Vbv/cif/qv//9+//////////03v/Yev/Zfv/14//25v/Uav/Vbv/46//////dkf/gmP/////04P/25//pvP/sxf/////lr//ouP/qwP/tyf/msv/ntf/+/P/36f/LUf/36P/w0v/w0//w0//w0//78//gm//QZv/RZv/gm//78v/////14v/nt//gnP/hn//w0f/////w0f/hn//gnP/nt//14v/////////////////LLv/MGv/PGf/LL//LG//THP/THv/SHv/UHv/LGv/LH/7SHuK8JOzDIuW+I+jAI//LHv/PTP/NF/PBG3BkOpyGMvrOH4R0NoV0NvzJGv/MF//QT//MLv/LGPu/FNayJu7FIdq2Jf7DFP/JF//ML//LJurCIsCiKujCIubAI7+hK/DHIf/LJ//HK//NGf/SHeS9IlxSP25QQmtOQmVZPu3DIf/RHf/HLP++Kf/AD/++EP3EFNCfLNhpQthrQdinKv/FFP/AEP+/K/++Dv/BEv+/Ef/CE//MIf/NIP/MGf++D//KTP/FOP/DE//PG//PHP/JGP/EFP/EM//BDf/TH//GFP/CEP/DEP/EEv/BDv/MS//IJ//JHf/JHP/JP//IQf/IHP/IJv/LSf///7SHOh0AAABUdFJOUwAAAAAAAAAAAAAAAAAABiZCQykIAUGn3/Hy4q5KAwRy7vJ/Yfb7cR/X4ipkdpepAqi5mavM2z5v/pGTtZS2QtP4999bIGyry8yUR4fJzbJ2BRIRE9ZoIHEAAAABYktHRAH/Ai3eAAAAB3RJTUUH6AIGEyohVAr+rAAAARZJREFUGNNjYGBgZGTi4xcQFBJmZmRkYQDxRUTFxCUkpaRlZBkZQXw5eYWQ0LCw0HBFJWGgCCOrskpEZFR0dExkrKoaG1BAXSMuPiExOjopOSpFU4uRgV07NS09IzMqKzsnNy9fh4OBU7egsKi4JCo6ubSsvEJPlkHfoDIqqqq6prauPiqqwVCYgcuosam5pbWtvaOzq6nbWJZBy6Snt69/wsRJk6f0TZ1masZgbjF9xsxZhbPnzJ01c8a8+ZYMVgt6F5aHLly0eGHokqVTl1kz2CxYXhi1YuWq1WuiouauXWbLYGe/bv2GjZscHDdv2bh1m5MzA7eLq5u7h6eXoLePr5+/ENDpjBwBgYH6PIyMQcF8vIyMAKnZUpQQgaV4AAAAJXRFWHRkYXRlOmNyZWF0ZQAyMDI0LTAyLTA2VDE5OjQyOjI1KzAwOjAwybP6HAAAACV0RVh0ZGF0ZTptb2RpZnkAMjAyNC0wMi0wNlQxOTo0MjoyNSswMDowMLjuQqAAAAAodEVYdGRhdGU6dGltZXN0YW1wADIwMjQtMDItMDZUMTk6NDI6MzMrMDA6MDBAgVbbAAAAAElFTkSuQmCC&color=20BEFF"/></a>
<a href="https://doi.org/10.48550/arXiv.2412.01626"><img src="https://img.shields.io/static/v1?label=Paper&message=arXiv&color=green&logo=arxiv"></a>
[![License](https://img.shields.io/badge/License-CC%20BY%204.0-blue)](https://creativecommons.org/licenses/by/4.0/)

<img src="https://raw.githubusercontent.com/DataScienceUIBK/PlausibleQA/main/Images/Pipeline.png">

**PlausibleQA** is a large-scale QA dataset designed to evaluate and enhance the ability of Large Language Models (LLMs) in distinguishing between correct and highly plausible incorrect answers. Unlike traditional QA datasets that primarily focus on correctness, PlausibleQA provides candidate answers annotated with plausibility scores and justifications.

## 🗂 Overview

- **10,000** questions
- **100,000** candidate answers with plausibility scores
- **1,000,000** justifications
- **Designed for MCQA and QA Robustness Assessment (QARA)**

## 📥 Dataset Download
The dataset is available on [HuggingFace](https://huggingface.co/datasets/JamshidJDMY/PlausibleQA):
```
wget "https://huggingface.co/datasets/JamshidJDMY/PlausibleQA/resolve/main/PlausibleQA.json?download=true"
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

## 📂 Repository Structure

```
📂 WikiHint/                                                # 🗂 Dataset files
│   ├── 📄 Pipeline.png                                     # 📊 Dataset pipeline visualization
│   ├── 📄 training.json                                    # 📊 Training dataset (900 questions, 4500 hints)
│   ├── 📄 test.json                                        # 📊 Test dataset (100 questions, 500 hints)
│
├── 📂 Experiments/                                         # 🧪 Model-generated hints
│   ├── 📄 GPT-4-Vanilla-answer-agnostic.json
│   ├── 📄 GPT-4-Vanilla-answer-aware.json
│   ├── 📄 LLaMA-3.1-405b-Vanilla-answer-agnostic.json
│   ├── 📄 LLaMA-3.1-405b-Vanilla-answer-aware.json
│   ├── 📄 LLaMA-3.1-70b-FTwA-answer-aware.json
│   ├── 📄 LLaMA-3.1-70b-FTwoA-answer-agnostic.json
│   ├── 📄 LLaMA-3.1-70b-Vanilla-answer-agnostic.json
│   ├── 📄 LLaMA-3.1-70b-Vanilla-answer-aware.json
│   ├── 📄 LLaMA-3.1-8b-FTwA-answer-aware.json
│   ├── 📄 LLaMA-3.1-8b-FTwoA-answer-agnostic.json
│   ├── 📄 LLaMA-3.1-8b-Vanilla-answer-agnostic.json
│   ├── 📄 LLaMA-3.1-8b-Vanilla-answer-aware.json
│
├── 📂 HintRank/                                            # 🏆 Hint ranking method
│   ├── 📄 EvaluationMethod.png                             # 📊 Visualization of HintRank evaluation method
│   ├── 📄 hint_rank.py                                     # 📜 HintRank implementation
│
├── 📂 HumanEvaluation/                                     # 👨‍🔬 Human evaluation data
│   ├── 📂 Person_1/  
│   │   ├── 📑 Part_1.xlsx
│   │   ├── 📑 Part_2.xlsx
│   │   ├── 📑 Part_3.xlsx
│   │   ├── 📑 Part_4.xlsx
│   │   ├── 📑 Part_5.xlsx
│   │   ├── 📑 Part_6.xlsx
│   │   ├── 📑 Part_7.xlsx
│   │   ├── 📑 Part_8.xlsx
│   │   ├── 📑 Part_9.xlsx
│   │   ├── 📑 Part_10.xlsx
│   │
│   ├── 📂 Person_2/ (Same structure as Person_1)
│   ├── 📂 Person_3/ (Same structure as Person_1)
│   ├── 📂 Person_4/ (Same structure as Person_1)
│   ├── 📂 Person_5/ (Same structure as Person_1)
│
└── 📘 README.md                                            # 📖 This file
```

## 📜 License

This project is licensed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**. You are free to use, share, and adapt the dataset with proper attribution.


## 📑 Citation

If you find this work useful, please cite [📜our paper](https://doi.org/10.48550/arXiv.2412.01626):

Mozafari, J., Gerhold, F., & Jatowt, A. (2024). WikiHint: A Human-Annotated Dataset for Hint Ranking and Generation. arXiv preprint arXiv:2412.01626.

### 📄 BibTeX:
```bibtex
@article{mozafari2025wikihinthumanannotateddatasethint,
      title={WikiHint: A Human-Annotated Dataset for Hint Ranking and Generation}, 
      author={Jamshid Mozafari and Florian Gerhold and Adam Jatowt},
      year={2025},
      eprint={2412.01626},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      doi={10.48550/arXiv.2412.01626}, 
}
```

