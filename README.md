# Fighting Bias with Bias: Promoting Model Robustness by Amplifying Dataset Biases
[**Paper**](https://arxiv.org/pdf/2305.18917.pdf) | [**Bias-amplified Splits on 🤗 Hugging Face Hub**](https://huggingface.co/bias-amplified-splits)

This repository contains the code and data for [Fighting Bias with Bias: Promoting Model Robustness by Amplifying Dataset Biases](https://arxiv.org/abs/2305.18917).

Bias-amplified splits are a new evaluation framework to assess model robustness by amplifying dataset biases in the training data and challenging models to generalize beyond them.
This framework is defined by a bias-amplified training set and a hard, anti-biased test set, which are automatically extracted from existing datasets using model-based methods.

![Our approach](./figures/method.png)

Such splits can be created for any dataset automatically, complementing the dataset's main training and test splits with challenging evaluation settings to promote more robust methods.

## Data
The bias-amplified splits created in the paper (for MultiNLI, Adversarial NLI, WANLI and QQP) are available at the [HF hub](https://huggingface.co/bias-amplified-splits).

Example for loading the data:
```
from datasets import load_dataset

# choose which bias detection method to use for the bias-amplified splits: either "minority_examples" or "partial_input"
dataset = load_dataset("bias-amplified-splits/wanli", "minority_examples")

# use the biased training split and anti-biased test split
train_dataset = dataset['train.biased']
eval_dataset = dataset['test.anti_biased']
```

## Code
Code for creating bias-amplified splits for other datasets coming soon ⏰.
In the meantime, please feel free to contact Yuval Reif at yuval.reif@mail.huji.ac.il.

## 📘Citation
Please cite the following if you our work useful in your research.
```
@article{reif2023fighting,
  title={Fighting Bias with Bias: Promoting Model Robustness by Amplifying Dataset Biases},
  author={Reif, Yuval and Schwartz, Roy},
  journal={arXiv preprint arXiv:2305.18917},
  year={2023}
}
```

## Contact Us
For questions and usage issues, please contact `yuval.reif@mail.huji.ac.il`.
