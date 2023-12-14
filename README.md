# User-Controllable Recommendation Against Filter Bubbles (reproduced work)

A reproduced version of the original paper [User-controllable Recommendation Against Filter Bubbles](https://dl.acm.org/doi/10.1145/3477495.3532075#sec-supp) will be implemented with the following dependencies:

- Python 3.7.3
- pytorch 1.4.0
- numpy 1.16.4
  
## Usage

### Data

- The three datasets are released in the './data' folder.

### Code

- The code for training and inference is in the './code' folder. 
- FM and NFM are first well trained, and then UCI is used for inference. 
- We have user-feature controls (i.e., C-UCI and F-UCI), and item-feature controls (i.e., Reranking, C-UCI, and F-UCI).

#### FM and NFM Training
```
python main.py --model=$1 --dataset=$2 --hidden=$3 --layers=$4 --lr=$5 --batch_size=$6 --dropout=$7 --lamda=$8 --batch_norm=$9 --epochs=$10 --log_name=$11 --gpu=$12
```
- The explanation of hyper-parameters can be found in './code/FM_NFM/main.py'. 
- The well trained models are provided in './code/FM_NFM/best_models'. We have tuned the hyper-parameters and chosen the best ones.

### UCI Inference

#### item-feature controls
- Reranking
```
cd item_controls/Reranking
python UCI_reranking.py --model=FM --dataset=ml_1m
```

- Fine-grained and coarse-grained item-feature controls
```
cd item_controls/fine_coarse_UCI
python C_UCI_inference.py --model=FM --dataset=ml_1m
python F_UCI_inference.py --model=NFM --dataset=amazon_book
```

#### user-feature coarse-grained controls
- UCI and maskUF for FM and NFM
```
cd user_coarse_controls
python UCI_coarse_user_control.py --model=FM
```

- Inference for vanilla FM and NFM
```
python FM_NFM_inference.py --model=FM
```
Note that we only use DIGIX for the experiments of user-feature controls.

#### user-feature fine-grained controls
- UCI and changeUF for FM and NFM
```
cd user_fine_controls
python UCI_fine_user_control.py --model=FM
```

- Inference for vanilla FM and NFM
```
python FM_NFM_inference.py --model=FM
```





@inproceedings{10.1145/3477495.3532075,
author = {Wang, Wenjie and Feng, Fuli and Nie, Liqiang and Chua, Tat-Seng},
title = {User-Controllable Recommendation Against Filter Bubbles},
year = {2022},
isbn = {9781450387323},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3477495.3532075},
doi = {10.1145/3477495.3532075},
abstract = {Recommender systems usually face the issue of filter bubbles: over-recommending homogeneous items based on user features and historical interactions. Filter bubbles will grow along the feedback loop and inadvertently narrow user interests. Existing work usually mitigates filter bubbles by incorporating objectives apart from accuracy such as diversity and fairness. However, they typically sacrifice accuracy, hurting model fidelity and user experience. Worse still, users have to passively accept the recommendation strategy and influence the system in an inefficient manner with high latency, e.g., keeping providing feedback (e.g., like and dislike) until the system recognizes the user intention.This work proposes a new recommender prototype called User-Controllable Recommender System (UCRS), which enables users to actively control the mitigation of filter bubbles. Functionally, 1) UCRS can alert users if they are deeply stuck in filter bubbles. 2) UCRS supports four kinds of control commands for users to mitigate the bubbles at different granularities. 3) UCRS can respond to the controls and adjust the recommendations on the fly. The key to adjusting lies in blocking the effect of out-of-date user representations on recommendations, which contains historical information inconsistent with the control commands. As such, we develop a causality-enhanced User-Controllable Inference (UCI) framework, which can quickly revise the recommendations based on user controls in the inference stage and utilize counterfactual inference to mitigate the effect of out-of-date user representations. Experiments on three datasets validate that the UCI framework can effectively recommend more desired items based on user controls, showing promising performance w.r.t. both accuracy and diversity.},
booktitle = {Proceedings of the 45th International ACM SIGIR Conference on Research and Development in Information Retrieval},
pages = {1251–1261},
numpages = {11},
keywords = {counterfactual inference, causal recommendation, user-controllable recommender systems, filter bubbles},
location = {<conf-loc>, <city>Madrid</city>, <country>Spain</country>, </conf-loc>},
series = {SIGIR '22}
}
