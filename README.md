This is a copy of repository : https://github.com/facebookresearch/SlowFast/ with modifications to allow inference on python 3.10.12

Refer to yaml, pkl files inside myconfig folder

Steps to run on Google Colab

!pip install -U torch torchvision cython

!pip install -U 'git+https://github.com/facebookresearch/fvcore.git' 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'

!git clone https://github.com/facebookresearch/detectron2 detectron2_repo

!pip install -e detectron2_repo

!git clone --recursive https://github.com/pytorch/pytorch

!git clone [https://github.com/facebookresearch/slowfast](https://github.com/shivanis1406/slowfastnetworks_inference)

!export PYTHONPATH=/path/to/SlowFast/slowfast:$PYTHONPATH

%cd slowfast

!pip3 install scikit-learn

!pip3 install Pillow

!pip3 install -e .

!pip install "git+https://github.com/facebookresearch/pytorchvideo.git"

Finally run inference on T4 GPU
!python3 tools/run_net.py --cfg /content/SLOWFAST_32x2_R101_50_50.yaml

