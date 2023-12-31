# Generating Less Certain Adversarial Examples Improves Robust Generalization

Code for our paper _Generating Less Certain Adversarial Examples Improves Robust Generalization_ by [Minxing Zhang](https://scholar.google.com/citations?user=wsSLja0AAAAJ&hl=en&oi=ao), [Michael Backes](https://scholar.google.com/citations?user=ZVS3KOEAAAAJ&hl=en&oi=ao), and [Xiao Zhang](https://scholar.google.com/citations?user=L-lz7CUAAAAJ&hl=en&oi=ao).

***

## News

Oct. 6, 2023 - We created this repo and our code will be released soon.

Oct. 7, 2023 - We uploaded the codes of the AT-EDAC on CIFAR-10 and the evaluation by AutoAttack.

Oct. 26, 2023 - We uploaded the codes of the TRADES-EDAC and MART-EDAC.

Dec. 6, 2023 - We uploaded the pre-trained WideResNet-34-10 model of TRADES-EDAC on CIFAR-10.

Dec. 27, 2023 - We uploaded the pre-trained WideResNet-34-10 model of MART-EDAC on CIFAR-10.

***

## Abstract

Recent studies have shown that deep neural networks are vulnerable to adversarial examples. Numerous defenses have been proposed to improve model robustness, among which adversarial training is most successful. In this work, we revisit the robust overfitting phenomenon. In particular, we argue that overconfident models produced during adversarial training could be a potential cause, supported by the empirical observation that the predicted labels of adversarial examples generated by models with better robust generalization ability tend to have significantly more even distributions. Based on the proposed definition of adversarial certainty, we incorporate an extragradient step in the adversarial training framework to search for models that can generate adversarially perturbed inputs with lower certainty, further improving robust generalization. Our approach is general and can be easily combined with other variants of adversarial training methods. Extensive experiments on image benchmarks demonstrate that our method effectively alleviates robust overfitting and is able to produce models with consistently improved robustness.

***

## Our Code

To improve robust generalization, we propose a novel **E**xtragradient-type method to explicitly **D**ecrease **A**dversarial **C**ertainty, i.e., **EDAC**.

Our implementations of EDAC-based adversarial training (AT-EDAC) on CIFAR-10 is ``./at_edac_cifar10.py``, and the evaluation by AutoAttack is ``./eval_autoattack.py``.

### Usage

To train AT-EDAC on CIFAR-10:
```text
python at_edac_cifar10.py --model {OnWhichModelArchitecture}
```

To train TRADES-EDAC on CIFAR-10:
```text
python trades_edac_cifar10.py --model {OnWhichModelArchitecture}
```

To train MART-EDAC on CIFAR-10:
```text
python mart_edac_cifar10.py --model {OnWhichModelArchitecture}
```

To evaluate on CIFAR-10:
```text
python eval_autoattack.py --arch {OnWhichModelArchitecture} --data CIFAR10
```

### Trained Model

The PreActResNet-18 trained by AT-EDAC on CIFAR-10: [https://drive.google.com/file/d/1xC3kAMY5tHWSF3F2NNHRyPt4FerHYX1l/view?usp=sharing](https://drive.google.com/file/d/1xC3kAMY5tHWSF3F2NNHRyPt4FerHYX1l/view?usp=sharing).

The WideResNet-34-10 trained by AT-EDAC on CIFAR-10: [https://drive.google.com/file/d/1yMm_WGLz53ka6rn0x0SgqNTD9fYJxL-Q/view?usp=sharing](https://drive.google.com/file/d/1yMm_WGLz53ka6rn0x0SgqNTD9fYJxL-Q/view?usp=sharing).

The WideResNet-34-10 trained by TRADES-EDAC on CIFAR-10: [https://drive.google.com/file/d/1jpKOqoOpVi7yGvDGnaH4Q3xP5QDLfzrE/view?usp=sharing](https://drive.google.com/file/d/1jpKOqoOpVi7yGvDGnaH4Q3xP5QDLfzrE/view?usp=sharing).

The WideResNet-34-10 trained by MART-EDAC on CIFAR-10: [https://drive.google.com/file/d/1TSRx8TTVGS0XtELPCg2jP-2TH34h_IPl/view?usp=sharing](https://drive.google.com/file/d/1TSRx8TTVGS0XtELPCg2jP-2TH34h_IPl/view?usp=sharing).

***

## Reference Code
1. Robust Overfitting: [https://github.com/locuslab/robust_overfitting](https://github.com/locuslab/robust_overfitting)
2. TRADES: [https://github.com/yaodongyu/TRADES](https://github.com/yaodongyu/TRADES)
3. MART: [https://github.com/YisenWang/MART/tree/master](https://github.com/YisenWang/MART/)
4. AutoAttack: [https://github.com/fra31/auto-attack](https://github.com/fra31/auto-attack)
