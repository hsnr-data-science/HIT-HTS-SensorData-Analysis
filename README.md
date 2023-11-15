# ICPS-Supporting-Material

The deep convolutional network’s computations is performed within the SEDAR framework on a system running Ubuntu 20.04 with a Intel(R) Xeon(R) Gold 6230R CPU @ 2.10GHz with 512 GB of RAM and NVIDIA Quadro RTX 8000 (4608 Cuda cores) with a graphics memory of 48 GB. 
On the software side a JupyterHub hosted within a Kubernetes Cluster running Python 3.8.8, TensorFlow 2.12.0, CUDA 11.4 is used. 
The Adam optimizer (learning rate of 0.001) and a batch size of 16 is chosen for a total of 200 epochs.
