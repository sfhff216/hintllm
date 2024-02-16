# HSP
Code and data accompanying our paper ["Hint-before-Solving Prompting: Guiding LLMs to
Effectively Utilize Encoded Knowledge"]() in [ACL 2024]().


## Get started
We suggest using miniconda/conda to set up the environment base python3.10. 
After create your env, you'll need install vllm.
```
conda activate your_env
pip install vllm

```

 

## Repo Structure
- `data/`: Evaluation datasets. 
- `icl_robust/`: robust analysis examples.
- `prompt/`: SD,LtM,PS,CoT,*Hint prompts for the LM to generate the reasoning chain.
- `sft/`:
  - `deepspeed_config.json`: We use deepspeed to help train model.
  - `sft_data_*.jsonl`: Sft datasets.
  - `sft_train.py`: The main train class.
  - `sft_train.sh`: Run this file to train model.  
- `evaluate.py`: Use this script evaluate the model output file to get accuracy.
- `inference.py`: Run the model to make predictions on a dataset.
- `produce_hintV2.py`: First generate hint and then generate solution.
- `produce_hintV2_gpt.py`: Use gpt4's hint to generate solution.

## Usage

### Make predictions

Run `inference.py`:

Example:
```
python inference.py --model {model_path} --tp_degree 4 --dataset_name GSM8K --output_path gsm8k_output.json --hint
```

### Evaluate the model predictions
Run `evaluate.py`

The accuracy will be printed to stdout.

Example:
```
python evaluate.py --dataset_name GSM8K --file gsm8k_output.json
```


## Citation
If you find this repository useful, please cite our paper:
```
@article{,
  title={Hint-before-Solving Prompting: Guiding LLMs to
Effectively Utilize Encoded Knowledge},
  author={},
  journal={},
  year={}
}
```


