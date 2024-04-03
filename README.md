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
screenshot of prompt_type = 2, N =8, ARC-Easy
![image](https://github.com/DanisHaiguerre/3036196219/blob/main/v2k8easy.png)
screenshot of prompt_type = 2, N =8, ARC-Challenge
![image](https://github.com/DanisHaiguerre/3036196219/blob/main/v2k8clg.png)

## 4. Modified files details 

