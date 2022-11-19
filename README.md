# POI-Prompt-Learning
This is my on-going project, which is extension of **[Time as Prompt for A Geography-aware Next Location Recommendation Framework](https://github.com/haoyi-duan/TPG)**.

## Introduction

In our previous work, the experimental results on four benchmark datasets demonstrated the superiority of our proposed framework **TPG** comparing with other state-of-the-art methods. The results indicated that **temporal signal** of next location is of great significance. We also demonstrate through ablation studies that our proposed **shifted window** mechanism is capable of overcoming defects of previous approaches.
![promptlearning](https://user-images.githubusercontent.com/58615742/202865249-a9296cd8-db44-4b70-abf1-5732cb786dac.jpg)


In the light of this fact, we plan to transfer prompt into more intelligent
one. Large-scale pre-trained models from NLP communities have demonstrated unlimited potential. We can consider to combine POI recommendation with language pre-trained models through prompt. Inspired by previous work [P-tuning v2](https://arxiv.org/abs/2110.07602), we design **continuous prompt** and **discrete prompt**. For continuous prompt, we transfer stop words to pseudo prompts, and for discrete prompt, I have proposed some templates:

```
{"relation": "P01", "template": "On [X_w] [X_ap] [X_t], user [X_u] may go to [MASK] ."}
{"relation": "P02", "template": "What do you think user [X_u] may go next on [X_w] [X_ap] [X_t] ? Answer: [MASK] ."}
{"relation": "P03", "template": "User [X_u] will go to location [MASK] on [X_w] [X_ap] [X_t] ."}
{"relation": "P04", "template": "User: [X_u], Time: [X_w] [X_ap] [X_t], Location: [MASK] ."}
{"relation": "P05", "template": "Time: [X_w] [X_ap] [X_t] [MASK]."}
```

Where 'X_w', 'X_ap', 'X_t' denote weekday, time description, and exact time; 'X_u' denotes user ID; 'Y_p' denotes POI. For example, for relation 'P01', possible template case can be "On Sunday morning 9:43, user 89 may go to [MASK]".

## Results

I'm still refining both the idea and experiments.
