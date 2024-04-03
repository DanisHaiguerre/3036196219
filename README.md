# HKU-DASC7606-A2
3036196219 LYU Jianing

## 1. Commands in order

**Use prompt_type "v2.0" because this part of the code in `eval_fewshot.py` and `eval_fewshot_multigpu.py` has been completed.

ARC-Easy

```
python eval_fewshot.py --data_path "data/ARC-Easy-validation.jsonl" --device_id "0,1" --model /userhome/cs2/jnlyu/localdir/phi-1_5 --embedder /userhome/cs2/jnlyu/localdir/bge-small-en-v1.5 --start_index 0 --end_index 9999 --max_len 1024 --output_path /userhome/cs2/jnlyu/v2k8easy4 --overwrite False --prompt_type "v2.0" --N 8 --top_k True --top_k_reverse False
```

```
python eval_fewshot.py --data_path "data/ARC-Easy-test.jsonl" --device_id "0,1" --model /userhome/cs2/jnlyu/localdir/phi-1_5 --embedder /userhome/cs2/jnlyu/localdir/bge-small-en-v1.5 --start_index 0 --end_index 9999 --max_len 1024 --output_path /userhome/cs2/jnlyu/v2k8easy4 --overwrite False --prompt_type "v2.0" --N 8 --top_k True --top_k_reverse False
```
ARC-Challenge
```
python acc.py --prediction_path /userhome/cs2/jnlyu/v2k8easy4
```

```
python eval_fewshot.py --data_path "data/ARC-Challenge-validation.jsonl" --device_id "0,1" --model /userhome/cs2/jnlyu/localdir/phi-1_5 --embedder /userhome/cs2/jnlyu/localdir/bge-small-en-v1.5 --start_index 0 --end_index 9999 --max_len 1024 --output_path /userhome/cs2/jnlyu/v2k8clg4 --overwrite False --prompt_type "v2.0" --N 8 --top_k True --top_k_reverse False
```

```
python eval_fewshot.py --data_path "data/ARC-Challenge-test.jsonl" --device_id "0,1" --model /userhome/cs2/jnlyu/localdir/phi-1_5 --embedder /userhome/cs2/jnlyu/localdir/bge-small-en-v1.5 --start_index 0 --end_index 9999 --max_len 1024 --output_path /userhome/cs2/jnlyu/v2k8clg4 --overwrite False --prompt_type "v2.0" --N 8 --top_k True --top_k_reverse False
```

```
python acc.py --prediction_path /userhome/cs2/jnlyu/v2k8clg4
```

## 2. Modified files
1. `download.py`
2. `modeling_phi.py`
3. `eval_fewshot.py` and `eval_fewshot_multigpu.py` 

## 3. Acc results

| parameters  | ARC-Easy | ARC-Challenge |  Weighted  |
| :--- | :--- | :--- | :--- |
| prompt_type = 1  N =8  | 0.6662  | 0.4799 |  0.53579  |
| prompt_type = 2  N =8   | 0.7975  | 0.5311 |  0.61102  |
| prompt_type = 1  N =5  | 0.65824  | 0.4722 |  0.528012  |
| prompt_type = 2  N =5   | 0.7861  | 0.5191 |  0.5992  |

![image](https://github.com/DanisHaiguerre/3036196219/blob/main/v2k8easy.png)
![image](https://github.com/DanisHaiguerre/3036196219/blob/main/v2k8clg.png)

Details:




Your report should comprise an introduction, methodology, and experiments section. Detail how you improved the model, considering options like:

+ Hyper-parameter Tuning: Explore critical hyper-parameters like the number of examples in the prompt, and the selection of top k similar examples based on embedding similarity.
+ Pre-trained Models for Embedding: Experiment with advanced neural networks or customize your own for embedding demonstrations and questions.
+ Formats of In-Context Demonstrations: Experiment with different demonstration formats and augment questions with relevant external knowledge, inspired by [this paper](https://arxiv.org/abs/2005.00700).
+ Expanding Context Length: Address limitations on context length by including more demonstrations or modifying embeddings for longer sequences, drawing on [this paper](https://arxiv.org/abs/2306.15595).

In the method section, describe the approaches you used to improve the baseline model performance. In the experiment section, analyze the dataset statistics, qualitative evaluations of the model's performance, and case analysis. 




2. Codes

    2.1 All the codes.
    
    2.2 README.txt that describes which python file has been added/modified.

3. Model Predictions on the Test Set (Submit in a zip file)


If your student id is 30300xxxxx, then the file should be organized as follows:

        30300xxxxx.zip
        |-report.pdf
        |-src
        |   |-README.md
        |   |-your code
        |-model_predictions.zip


- 10% for late assignments submitted within 1 day late. 
- 20% for late assignments submitted within 2 days late.
- 50% for late assignments submitted within 7 days late.
- 100% for late assignments submitted after 7 days late.

