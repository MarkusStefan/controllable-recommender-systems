# controllable-recommender-systems

A reproduced version of the original paper [User-controllable Recommendation Against Filter Bubbles]{https://dl.acm.org/doi/10.1145/3477495.3532075#sec-supp} will be implemented with the following dependencies:







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
