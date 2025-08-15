# Gender Representation Bias Quantification in Gendered Language Corpora

Repository accompanying our paper titled **Leveraging Large Language Models to Measure Gender Representation Bias in Gendered Language Corpora**, presented at the **6th Workshop on Gender Bias in Natural Language Processing at ACL 2025**. The research and experimental evaluation has been conducted for Spanish and Valencian.

**Paper Authors:** Erik Derner, Sara Sansalvador de la Fuente, Yoan Gutiérrez, Paloma Moreda, Nuria Oliver

**Code and Data Authors:** Erik Derner, Sara Sansalvador de la Fuente, Elena Maestre Hernández + sampled data from [OPUS](https://opus.nlpl.eu/)

**Contact:** erik@ellisalicante.org

## Repository Structure

- `code`: Code for dataset analysis, continual pretraining, inference, and validation
  - `bias-quantification`: Gender representation bias quantification in a given dataset
  - `continual-pretraining`: Continual pretraining and model inference to evaluate how gender representation bias in training data propagates to the model inference
  - `validation`: Validation of the gender representation bias quantification method on an annotated dataset
- `data`: Samples of corpora, annotated datasets, prompts, few-shot examples, word skiplist, and stories for continual pretraining
  - `continual-pretraining`: Biased and balanced stories datasets generated for continual pretraining experiments
  - `corpora-en-es`: Samples of aligned parallel corpora in English and Spanish used in the experiments in the paper
  - `dataset-analysis`: Prompts, few-shot examples, and skiplist for bias evaluation
  - `validation`: Annotated (ground truth) data for gender representation bias quantification method validation

## Getting Started

### Prerequisites

- Python 3.12
- CUDA 12.1 to use GPU

### Installation

1. Clone or download the repository.

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Set the environment variables if you want to use API inference with either of the providers:
    - `OPENAI_API_KEY` – OpenAI API key
    - `GROQ_API_KEY` – Groq API key

## Usage

### Gender Representation Bias Quantification

In `code/bias-quantification`, use:
- `dataset-analysis-openai.ipynb` to analyze datasets in gendered languages using OpenAI API
- `dataset-analysis-groq.ipynb` to analyze datasets in gendered languages using Groq API
- `dataset-analysis-gp.ipynb` to analyze datasets in English using the Gender Polarity method

### Sample Subset Extraction from a Corpus

To extract a sample subset from a (potentially multilingual aligned) text corpus, use `dataset-extraction.ipynb` in `code/bias-quantification`.

### Continual Pretraining and Inference

In `code/continual-pretraining`, use:
- `continual-pretraining.ipynb` to continually pretrain a HuggingFace model on a given raw text dataset
- `inference.ipynb` to run inference with a base or continually pretrained model

### Validation

To validate the gender representation bias quantification method on an annotated dataset, use in `code/validation`:
-  `validation-gt-openai.ipynb` to perform the validation using OpenAI API
-  `validation-gt-groq.ipynb` to perform the validation using Groq API

## License

This project is licensed under the MIT License. See the [LICENSE.txt](LICENSE.txt) file for details.

## Citation

If you use this code or data, please cite our paper:

```bibtex
@inproceedings{derner2025leveraging,
  author    = {Derner, Erik and Sansalvador de la Fuente, Sara and Guti{\'e}rrez, Yoan and Moreda, Paloma and Oliver, Nuria},
  title     = {Leveraging Large Language Models to Measure Gender Representation Bias in Gendered Language Corpora},
  booktitle = {Proceedings of the 6th Workshop on Gender Bias in Natural Language Processing (GeBNLP)},
  pages     = {468--483},
  publisher = {Association for Computational Linguistics},
  address   = {Vienna, Austria},
  year      = {2025},
  month     = {Aug}
}
```
