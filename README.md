# Interpreting Indirect Answers to Yes-No Questions in Multiple Languages
The repository for EMNLP 2023 finding paper: [Interpreting Indirect Answers to Yes-No Questions in Multiple Languages](https://aclanthology.org/2023.findings-emnlp.146/)

# Dataset 

The dataset is available under folder [data](https://github.com/wang-zijie/yn-question-multilingual/tree/main/data), including [training dataset](https://github.com/wang-zijie/yn-question-multilingual/tree/main/data/train_dataset), and [benchmark (dev + test)](https://github.com/wang-zijie/yn-question-multilingual/tree/main/data/test_dataset).


## Training Dataset Statistics

|                   | Hindi | Korean | Chinese | Bangla | Turkish | Spanish | Nepali | Persian |
|------------------:| -----:| ------:|  ------:| ------:|  ------:|  ------:| ------:|  ------:|
| Training instance | 3,109 | 12,976 | 77,128  |   n/a  | 275,732 |  1,489  | n/a    |   n/a   |
|              % yes|  27.0 | 92.0   | 57.7    |   n/a  |   94.4  |    60.1 | n/a    |   n/a   |
|               % no|  73.0 |  8.0   | 42.3    |  n/a   |    5.6  |  39.1   |  n/a   |   n/a   |


## Benchmark (validation and test) Dataset Statistics
|                   | Hindi | Korean | Chinese | Bangla | Turkish | Spanish | Nepali | Persian |
|------------------:| -----:| ------:|  ------:| ------:|  ------:|  ------:| ------:|  ------:|
| Benchmark instance|  300  |   300  |    600  |   300  |   600   |   300   |   300  |   300   |
|              % yes|  44.4 |  52.7  | 38.5    |  34.3  |   43.7  |   54.2  |  46.7  |   46.7  |
|               % no|  43.3 |  27.3  | 30.5    |  32.0  |   32.7  |   12.0  |  36.3  |   32.0  |
|           % middle|  12.7 |  20.0  | 31.0    |  33.7  |   23.6  |   32.8  |  17.0  |   21.3  |


## Dataset Fields
* ```pre_turn_n (only for some datasets):``` dialogue turn before the yes-no question (if available). 4 turns (from pre_sent_1 to pre_sent_4) are included.
* ```question:``` The yes-no question.
* ```answer:``` The answer to the yes-no question (the turn immediately after the question turn).
* ```aft_turn_n (only for some datasets):``` dialogue turn after the yes-no question (if available). 4 turns (from aft_sent_1 to aft_sent_4) are included.
* ```label:``` The interpretation of the answer. For answers in the training dataset, the interpretation is based on the keyword extraction and thus can only be ```yes``` or ```no```. For answers in the benchmark dataset, the interpretation is made by human annotators and can be ```yes```, ```no``` or ```middle (neither yes nor no)```.
<!-- # Requirements

Install required packages
```
pip install --upgrade pip
pip install -r ./requirements.txt
``` -->

# Citation

```
@inproceedings{wang-etal-2023-interpreting,
    title = "Interpreting Indirect Answers to Yes-No Questions in Multiple Languages",
    author = "Wang, Zijie  and
      Hossain, Md  and
      Mathur, Shivam  and
      Melo, Terry  and
      Ozler, Kadir  and
      Park, Keun  and
      Quintero, Jacob  and
      Rezaei, MohammadHossein  and
      Shakya, Shreya  and
      Uddin, Md  and
      Blanco, Eduardo",
    editor = "Bouamor, Houda  and
      Pino, Juan  and
      Bali, Kalika",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2023",
    month = dec,
    year = "2023",
    address = "Singapore",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.findings-emnlp.146",
    pages = "2210--2227",
    abstract = "Yes-no questions expect a yes or no for an answer, but people often skip polar keywords. Instead, they answer with long explanations that must be interpreted. In this paper, we focus on this challenging problem and release new benchmarks in eight languages. We present a distant supervision approach to collect training data, and demonstrate that direct answers (i.e., with polar keywords) are useful to train models to interpret indirect answers (i.e., without polar keywords). We show that monolingual fine-tuning is beneficial if training data can be obtained via distant supervision for the language of interest (5 languages). Additionally, we show that cross-lingual fine-tuning is always beneficial (8 languages).",
}
```