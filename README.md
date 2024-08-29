
# Routing Project
The goal of this project is to compare acuuracy of finetuned [ALBERT[(https://arxiv.org/abs/1909.11942) type of model vs. [Semantic router](https://github.com/aurelio-labs/semantic-router/) in order to use it in narrowing down a context of the request and proper routing user's request to concrete handling


## Table of Contents
- [About](#about)
- [Results](#results)
- [License](#license)
- [Contact](#contact)

## About
I finetuned [vineetsharma/customer-support-intent-albert](https://huggingface.co/vineetsharma/customer-support-intent-albert) model with [bitext/Bitext-customer-support-llm-chatbot-training-dataset](https://huggingface.co/datasets/bitext/Bitext-customer-support-llm-chatbot-training-dataset) dataset.
The result of finetunig is [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   
For finetuning code see [Fine_tuning_Classification_for_Routing.ipynb](https://github.com/agdev/Routing/blob/main/Fine_tuning_Classification_for_Routing.ipynb)

With [Semantic router](https://github.com/aurelio-labs/semantic-router/) I used [semantic_router/encoders/HuggingFaceEncoder](https://github.com/aurelio-labs/semantic-router/blob/main/semantic_router/encoders/huggingface.py) whcih by default is using [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).

So essentially we are comparing [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)  vs. [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).
For comparison see [Routing_Comparison_Finetuned_vs_Semantic_Router.ipynb](https://github.com/agdev/Routing/blob/main/Routing_Comparison_Finetuned_vs_Semantic_Router.ipynb)

## Results
Accuracy wise performance of both models is almost identical, However in concrete application it might vary due to [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2). not able to classify some request that might be a positive or negative depends on needs of an application

| Model          | Data                        | Accuracy       |
|------------------|------------------------------------|--------------|
| [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   | Test dataset | 0.9996279069767442  |
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | Test dataset    | 0.9994418604651163  |
| [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   | Synthetic data created by LLM | 0.64  |
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | Synthetic data created by LLM    | 0.64  |


## Conculusion
Both models are very low in resource consumptions so definitely are good candidates. 
Given similar performance and no need to finetune a model I would start with [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2). and see what issues I encounter if any.

## License
![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)

## Contact
topexpertsolutions@gmail.com
