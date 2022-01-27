# Clinical-Longformer

<span style="font-size:larger;">**Clinical-Longformer**</span> is a clinical knowledge enriched version of Longformer that was further pre-trained using MIMIC-III clinical notes. It allows up to 4,096 tokens as the model input. Clinical-Longformer consistently out-perform ClinicalBERT across 10 baseline dataset for at least 2 percent. The dataset broadly cover NER, QA and text classification tasks. For more details, please refer to: s

### Pre-training
We initialized Clinical-Longformer from the pre-trained weights of the base version of Longformer. The pre-training process was distributed in parallel to 6 32GB Tesla V100 GPUs. FP16 precision was enabled to accelerate training. We pre-trained Clinical-Longformer for 200,000 steps with batch size of 6×3. The learning rates were 3e-5 for both models. The entire pre-training process took more than 2 weeks. 

### Usage
Load the model directly from Transformers:
```
from transformers import AutoTokenizer, AutoModelForMaskedLM
tokenizer = AutoTokenizer.from_pretrained("yikuan8/Clinical-Longformer", use_auth_token=True)
model = AutoModelForMaskedLM.from_pretrained("yikuan8/Clinical-Longformer", use_auth_token=True)
```

If you find our implementation helps, please consider citing this :)
```
@inproceedings{li2020comparison,
  title={A comparison of pre-trained vision-and-language models for multimodal representation learning across medical images and reports},
  author={Li, Yikuan and Wang, Hanyin and Luo, Yuan},
  booktitle={2020 IEEE International Conference on Bioinformatics and Biomedicine (BIBM)},
  pages={1999--2004},
  year={2020},
  organization={IEEE}
}
```

### Questions
Please email yikuanli2018@u.northwestern.edu or raise a issue.



