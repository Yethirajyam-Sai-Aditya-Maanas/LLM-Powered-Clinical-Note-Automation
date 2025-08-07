# LLM-Powered Clinical Note Automation: A Zero-Shot vs. Few-Shot Analysis

This project benchmarks the performance of the `mistralai/Mistral-7B-Instruct-v0.2` model on the task of generating clinical SOAP notes from doctor-patient dialogues. It directly compares the effectiveness of **zero-shot** prompting against **few-shot** prompting.

## 🎯 Problem Statement

In clinical settings, physicians spend a significant amount of time writing detailed notes after each patient interaction. This project explores the use of a Large Language Model (LLM) to automate this process, aiming to reduce administrative burden and improve efficiency by generating structured SOAP (Subjective, Objective, Assessment, Plan) notes directly from conversation transcripts.

## ✨ Key Features

* **Comparative Analysis:** Directly benchmarks zero-shot vs. few-shot performance.
* **Efficient Inference:** Implements 4-bit quantization (`bitsandbytes`) to run the 7-billion parameter model on consumer-grade hardware.
* **Robust Evaluation:** Uses both **ROUGE** (lexical overlap) and **BERTScore** (semantic similarity) to provide a comprehensive evaluation of the generated text.
* **Reproducibility:** The entire workflow, from data loading to evaluation, is captured in a single notebook with clear memory management.

## 🛠️ Tech Stack

* **Language:** Python
* **Core Libraries:** PyTorch, Hugging Face `transformers`, `accelerate`, `bitsandbytes`
* **Data Handling:** Pandas
* **Evaluation:** `rouge_score`, `bert_score`
* **Platform:** Kaggle Notebooks

## 📈 Results

The experiment demonstrated that providing the model with a few examples (**few-shot prompting**) significantly improved the quality of the generated notes compared to providing none (**zero-shot prompting**).

The few-shot approach yielded an **~12% increase in semantic similarity (BERTScore)** and a **~70% increase in lexical overlap (ROUGE-L)**, confirming its superior performance for this task.

| Metric | Zero-Shot F1-Score | Few-Shot F1-Score | Performance Uplift
| :--- | :--- | :--- |
| **BERTScore** | 0.799 | **0.894** | +11.9% |
| **ROUGE-L** | 0.221 | **0.375** | +69.7%

For a detailed qualitative comparison, please see the `generated_clinical_notes.csv` file.

## 🚀 How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    cd your-repo-name
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook "Your Notebook Name.ipynb"
    ```
    **Note:** You will need a GPU and a Hugging Face token set as an environment variable to run this notebook successfully.
