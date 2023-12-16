![](images/tat.png)
# Trojans Against Trojans (TAT)
This page provides the data (code coming soon) used in the following paper.

Mohamed E. Hussein, Sudharshan Subramaniam Janakiraman, and Wael AbdAlmageed, "_[Trojan Model Detection Using Activation Optimization](https://arxiv.org/abs/2306.04877)_".

The dataset contains 1,200 trained ViT-B-16 models, trained on ImageNet. Half of the models are benign. The other half constitutes Trojan models, each trained with a randomly generated trigger that makes the model predict a specific target class, chosen at random for each Trojan model.

# Download
The data can be downloaded from this [GoogleDrive folder](https://drive.google.com/drive/u/1/folders/14xaroC7RayfRxhPiM4uhdGqN5c04GFR7).

# Usage
The models are based on `torchvision`'s implementation of the ViT-B-16 architecture. We specifically used `PyTorch` version 2.0 and `torchvision` version 1.15.1. The following code snippet can be used to load any of the models in the dataset.

```python
import torch
from torchvision.models import vit_b_16

model_path = ...
model = vit_b_16()
model.load_state_dict(torch.load(model_path, map_location=lambda storage, loc: storage))
```

# Citation
If you use this dataset, please cite the following paper.

```
@misc{hussein2023trojan,
      title={Trojan Model Detection Using Activation Optimization}, 
      author={Mohamed E. Hussein and Sudharshan Subramaniam Janakiraman and Wael AbdAlmageed},
      year={2023},
      eprint={2306.04877},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```