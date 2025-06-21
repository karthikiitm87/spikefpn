
---

<h3 align="center"> SpikeFPN: Automotive Object Detection via Learning Sparse Events by Spiking Neurons </h3>

---

<p align="center">
  <picture>
    <img src="docs/source/_static/spikefpn-overview.jpg" alt="SpikeFPN Overview" height="440">
  </picture>
</p>

This work explores the membrane potential dynamics of spiking neural networks (SNNs) and their ability to process sparse, asynchronous events. We propose an innovative **spike-triggered adaptive threshold** mechanism that facilitates stable and effective training. Building on this foundation, we design a specialized **spiking feature pyramid network (SpikeFPN)** optimized for automotive event-based object detection. Comprehensive evaluations indicate that SpikeFPN achieves competitive performance compared to traditional SNNs and advanced artificial neural network (ANN) models while maintaining efficient computation.

- **Official publication** in *IEEE Transactions on Cognitive and Developmental Systems*:  
  [DOI: 10.1109/TCDS.2024.3410371](https://doi.org/10.1109/TCDS.2024.3410371)

- **Accepted manuscript** available on *arXiv*:  
  [arXiv:2307.12900](https://arxiv.org/abs/2307.12900)
  

## Environment Configuration

In a configuration utilizing `Ubuntu 22.04`, `CUDA 12.4`, and `PyTorch 2.3.1`:

```shell
apt-get update # If necessary
apt-get install ffmpeg libsm6 libxext6
pip install -r requirements.txt
```

## Experiment on GEN1 Automotive Detection (GAD) Dataset

### Data Preprocessing
```shell
python ./preprocess/gad_framing.py
```

### Training and Testing
```shell
python ./train_gad.py
python ./test_gad.py
```

## Experiment on N-CARS Dataset

### Data Preprocessing
```shell
python ./preprocess/ncars_framing.py
```

### Data Division
|                    | Class: background | Class: cars  |
| :----------------- | :---------------: | :----------: |
| **For Training**   |     0 ~ 4210      |   0 ~ 4395   |
| **For Validating** |    4211 ~ 5706    | 4396 ~ 5983  |
| **For Testing**    |   5707 ~ 11692    | 5984 ~ 12335 |

### Training and Testing
```shell
python ./train_ncars.py
python ./test_ncars.py
```

## Citation

```latex
@ARTICLE{spikefpn,
    author={Zhang, Hu and Li, Yanchen and Leng, Luziwei and Che, Kaiwei and Liu, Qian and Guo, Qinghai and Liao, Jianxing and Cheng, Ran},
    journal={IEEE Transactions on Cognitive and Developmental Systems}, 
    title={Automotive Object Detection via Learning Sparse Events by Spiking Neurons}, 
    year={2024},
    pages={1-15},
    doi={10.1109/TCDS.2024.3410371}
}
```

