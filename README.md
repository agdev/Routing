
# Routing Project
The goal of this project is to compare accuracy of fine-tuned [ALBERT](https://arxiv.org/abs/1909.11942) type of model vs. [Semantic router](https://github.com/aurelio-labs/semantic-router/) to optimize routing of a user's request/prompt


## Table of Contents
- [About](#about)
- [Results](#results)
- [License](#license)
- [Contact](#contact)

## About
I finetuned [vineetsharma/customer-support-intent-albert](https://huggingface.co/vineetsharma/customer-support-intent-albert) model using [bitext/Bitext-customer-support-llm-chatbot-training-dataset](https://huggingface.co/datasets/bitext/Bitext-customer-support-llm-chatbot-training-dataset) dataset.  
The fine-tuned model is [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   
For finetuning code see [Fine_tuning_Classification_for_Routing.ipynb](https://github.com/agdev/Routing/blob/main/Fine_tuning_Classification_for_Routing.ipynb)

With [Semantic router](https://github.com/aurelio-labs/semantic-router/) I used [HuggingFaceEncoder](https://github.com/aurelio-labs/semantic-router/blob/main/semantic_router/encoders/huggingface.py) with default model [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).

So essentially we are comparing [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)  vs. [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).  
For comparison code see [Routing_Comparison_Finetuned_vs_Semantic_Router.ipynb](https://github.com/agdev/Routing/blob/main/Routing_Comparison_Finetuned_vs_Semantic_Router.ipynb)

## Results
Accuracy wise performance of both models is almost identical, However in concrete application it might vary due to [Semantic router](https://github.com/aurelio-labs/semantic-router/) not able to classify some request that might be a positive or negative depends on needs of an application  

| Model          | Data                        | Accuracy       |
|------------------|------------------------------------|--------------|
| [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   | Test dataset | 0.9996279069767442  |
| [Semantic router](https://github.com/aurelio-labs/semantic-router/) | Test dataset    | 0.9994418604651163  |
| [AIEnthusiast369/customer-support-categ_classification-albert_v2](https://huggingface.co/AIEnthusiast369/customer-support-categ_classification-albert_v2)   | Synthetic data created by LLM | 0.64  |
| [Semantic router](https://github.com/aurelio-labs/semantic-router/) | Synthetic data created by LLM    | 0.64  |


## Conculusion
Both are resource-efficient. Given the similar performance, I recommend starting with [Semantic router](https://github.com/aurelio-labs/semantic-router/) due to its ease of use without additional fine-tuning.

## License
This project is licensed under the ![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)

## Contact
For any inquiries, please reach out to topexpertsolutions@gmail.com
