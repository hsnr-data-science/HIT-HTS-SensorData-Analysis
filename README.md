# Supporting-Material

This repo contains supporting information, code and the datasets for our publication [Coatings Intelligence: Data-driven Automation for
Chemistry 4.0](https://link.com).
---
## Code will be published soon!

## Materials and sample preparation
The training samples undergo manual coating with a two-component urethane-based base coating obtained from MIPA SE (Essenbach, Germany). This coating is chosen for its adjustable mechanical properties achieved by manipulating the ratios of its crosslinkers, HS 25 and MS 25, with HS 25 being the more reactive component. Using the provided materials, we prepare coatings with crosslinker weights ranging from 0 to 50 wt.% for MS 25 and 0 to 25 wt.% for HS 25, based on previous tests to prevent surface flaws. After speed-mixing at 2000 rpm for 60 seconds, the mixture is applied to degreased steel panels using an 80-micron bar. The panels are allowed to flash off at room temperature for 15 minutes and then oven-dried at 60°C for 30 minutes in preparation for scratch testing.

For the test set, we use a two-component, high-solid, urethane-based clear coating named MIPA 2K-HS-CC9, obtained from MIPA SE (Essenbach, Germany). The coating's formulation is optimized to include only one isocyanate crosslinker, MIPA MS 25. All materials are used as supplied without further purification. We vary the proportion of this crosslinker, maintaining it between 37.5 and 87.5 weight percent relative to the binder, to achieve varying degrees of scratch resistance. These samples are prepared using a state-of-the-art, fully automatic high-throughput system, the details of which are presented in the subsequent paragraph (see Section \ref{sec:automated_screening}), marking a shift from manual processing to an automated approach. This transition enhances the uniformity and reproducibility of the coatings applied to the test panels.

## Model Architecture
1. **Input Layer**
    - Batch Normalization: Normalizes the input along the feature axis, helping with training stability.
      - Input Shape: (519, 1)

2. **Convolutional Layers**
    - Conv1D (8 filters, kernel size 4, ReLU activation)
    - MaxPooling1D (pool size 2)
    - Conv1D (16 filters, kernel size 8, ReLU activation)
    - MaxPooling1D (pool size 2)
    - Conv1D (32 filters, kernel size 16, ReLU activation)
    - MaxPooling1D (pool size 2)

3. **Flatten Layer**
    - Flattens the output from the convolutional layers into a 1D array.

4. **Dense Layers**
    - Dense (256 neurons, ReLU activation)
    - Dense (128 neurons, ReLU activation)
    - Dense (64 neurons, ReLU activation)
    - Dense (32 neurons, ReLU activation)
    - Dense (1 neuron, linear activation)

## Training details of the neural net
The deep convolutional network’s computations is performed within the SEDAR framework on a system running Ubuntu 20.04 with a Intel(R) Xeon(R) Gold 6230R CPU @ 2.10GHz with 512 GB of RAM and NVIDIA Quadro RTX 8000 (4608 Cuda cores) with a graphics memory of 48 GB. 
On the software side a JupyterHub hosted within a Kubernetes Cluster running Python 3.8.8, TensorFlow 2.12.0, CUDA 11.4 is used. 
The Adam optimizer (learning rate of 0.001) and a batch size of 16 is chosen for a total of 200 epochs.



## License

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png


## Acknowledgments
Sayed Hoseini and Gaoyuan Zhang equally contribute to this paper. 
The authors acknowledge gratefully the cooperation with the HIT Institute which made this work possible. 
This work has been sponsored by the German Federal Ministry of Education and Research, Germany in the funding program “Forschung an Fachhochschulen”, project IDACH (grant no. 13FH557KX0, [i2DACH](https://www.hs-niederrhein.de/i2dach) ).


## Citing
If you use this work in your research or wish to refer to the baseline results published here, please use the following BibTeX entries:

```
@article{bibtex}
```

