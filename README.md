## This work is extended from EvadeML-Zoo (https://github.com/mzweilin/EvadeML-Zoo) to implement our paper "Feature Distillation DNN-Oriented JPEG Compression Against Adversarial Examples"
* We add our feature distillation defense method in ./utils
* Thanks for the decent code from EvadeML-Zoo
* If you use this code please cite our paper: 

@article{liu2018feature,
  title={Feature Distillation: DNN-Oriented JPEG Compression Against Adversarial Examples},
  author={Liu, Zihao and Liu, Qi and Liu, Tao and Wang, Yanzhi and Wen, Wujie},
  journal={arXiv preprint arXiv:1803.05787},
  year={2018}
}



## 1. Install dependencies.

```bash
pip install -r requirements_cpu.txt
```

If you are going to run the code on GPU, install this list instead:
```bash
pip install -r requirements_gpu.txt
```

## 2. Fetch submodules.
```bash
git submodule update --init --recursive
```

## 3. Download pre-trained models.
```bash
mkdir downloads; curl -sL https://github.com/mzweilin/EvadeML-Zoo/releases/download/v0.1/downloads.tar.gz | tar xzv -C downloads
```

## 4. Usage of `python main.py`
```
usage: python main.py [-h] [--model_name MODEL_NAME]
               [--select [SELECT]] [--noselect] [--nb_examples NB_EXAMPLES]
               [--balance_sampling [BALANCE_SAMPLING]] [--nobalance_sampling]
               [--test_mode [TEST_MODE]] [--notest_mode] [--attacks ATTACKS]


optional arguments:
  -h, --help            show this help message and exit
  --model_name MODEL_NAME
                        Supported: cleverhans, cleverhans_adv_trained and
                        carlini for MNIST; carlini and DenseNet for CIFAR-10;
                        ResNet50, VGG19, Inceptionv3 and MobileNet for
                        ImageNet.
  --select [SELECT]     Select correctly classified examples for the
                        experiement.
  --noselect
  --nb_examples NB_EXAMPLES
                        The number of examples selected for attacks.
  --balance_sampling [BALANCE_SAMPLING]
                        Select the same number of examples for each class.
  --nobalance_sampling
  --test_mode [TEST_MODE]
                        Only select one sample for each class.
  --notest_mode
  --attacks ATTACKS     Attack name and parameters in URL style, separated by
                        semicolon.
```

### 5. Example.
```bash
python main.py --model_name MobileNet --nb_examples 100 --attacks "fgsm?eps=0.0078"
```

