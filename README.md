# MoRe
Paper: Compositional Transformation Reasoning for Composed Video Retrieval
## 📢 News
The code is currently being organized and will be released soon.

**[2026.3.25]** The repository is created.

<a name="installation"></a>
## Installation
1. Clone the repository from GitHub.

```shell
git clone https://github.com/shhuangcoder/MoRe.git
cd MoRe
```

2. Create conda environment.

```shell
conda create -n MoRe python=3.8
conda activate MoRe
```


3. Download the packages
```shell
pip install -r requirements.txt
```
<a name="dataset"></a>

## Dataset
For the dataset, we provide the corresponding download link. Please follow the download instructions provided in the link to download the dataset.<br>
EgoCVR: https://github.com/ExplainableML/EgoCVR<br>
WebVid-CoVR: https://imagine.enpc.fr/~ventural/covr/<br>


## Association

```

```


## Stage-1 ROVCS

Please first use the EgoCVR project [TFR-CVR Stage1](https://github.com/ExplainableML/EgoCVR) to generate a LanguageBind-based unimodal candidate video ranking CSV file, and then extract the non-dominated solutions.


## Stage-2 MLLM Pairwise Reasoning

```
python Qwen_pairwise_reasoning.py
```
note: Since the inference for each query is independent, if you have multiple GPUs, you can divide the test set into N groups by setting the start_index and end_index parameters in the code, and perform inference in parallel to reduce the overall runtime.

Like:
```
CUDA_VISIBLE_DEVICES=0 nohup python Qwen_pairwise_reasoning.py --start_index 0    --end_index 574

CUDA_VISIBLE_DEVICES=1 nohup python Qwen_pairwise_reasoning.py --start_index 574  --end_index 1147

CUDA_VISIBLE_DEVICES=2 nohup python Qwen_pairwise_reasoning.py --start_index 1147 --end_index 1721

CUDA_VISIBLE_DEVICES=3 nohup python Qwen_pairwise_reasoning.py --start_index 1721 --end_index 2295
```

## Model Zoo
* You can download [Qwen2.5VL-7B-Instruct](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct)


## Citation
If you find the repository or the paper useful, please use the following entry for citation.
```

```

## Acknowledgement

The codebase is based on [EgoCVR](https://github.com/ExplainableML/EgoCVR).
We thank the authors for their efforts.
