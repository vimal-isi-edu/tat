![](images/tat.png)
# Trojans Against Trojans (TAT)
This page provides the data used in the following paper, which can be found [here](https://link.springer.com/chapter/10.1007/978-3-031-78122-3_23). An earlier version of the paper can be found on [arxiv](https://arxiv.org/pdf/2306.04877). The associated code can be found [here](https://github.com/vimal-isi-edu/trigs).

Mohamed E. Hussein, Sudharshan Subramaniam Janakiraman, and Wael AbdAlmageed, "TRIGS: Trojan Identification from Gradient-based Signatures", accepted at ICPR 2024.

The dataset contains 1,200 trained ViT-B-16 models, trained on ImageNet. Half of the models are benign. The other half constitutes Trojan models, each trained with a randomly generated trigger that makes the model predict a specific target class, chosen at random for each Trojan model.

# Download
The data can be downloaded from this [GoogleDrive folder](https://drive.google.com/drive/u/1/folders/10fsrNJaYBgDAq9uDVM6f0VPqdT_S921Z).

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
@inproceedings{HusseinICPR24TRIGS,
  author       = {Mohamed E Hussein and
                  Sudharshan Subramaniam Janakiraman and
                  Wael AbdAlmageed},
  title        = {{TRIGS:} Trojan Identification from Gradient-based Signatures},
  booktitle    = {27th International Conference on Pattern Recognition, {ICPR} 2024},
  publisher    = {{Springer}},
  year         = {2024},
}
```