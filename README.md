This is a copy of repository : https://github.com/facebookresearch/SlowFast/ with few bug fixes to allow inference on python 3.10.12 in a Colab environment

Refer to yaml file inside myconfig folder. Download pre-trained model file (.pkl) from https://dl.fbaipublicfiles.com/pyslowfast/model_zoo/ava/SLOWFAST_32x2_R101_50_50.pkl or https://github.com/facebookresearch/SlowFast/blob/main/MODEL_ZOO.md

Getting Started
```
pip install -U torch torchvision cython
pip install -U 'git+https://github.com/facebookresearch/fvcore.git' 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
git clone https://github.com/facebookresearch/detectron2 detectron2_repo
pip install -e detectron2_repo
git clone --recursive https://github.com/pytorch/pytorch
git clone https://github.com/shivanis1406/slowfastnetworks_inference
export PYTHONPATH=/path/to/SlowFast/slowfast:$PYTHONPATH
cd slowfastnetworks_inference
pip3 install scikit-learn
pip3 install Pillow
pip3 install -e .
pip install "git+https://github.com/facebookresearch/pytorchvideo.git"
```

Finally run inference on T4 GPU - 
Edit myconfig/SLOWFAST_32x2_R101_50_50.yaml 
1. Change the path to input video -> INPUT_VIDEO: "/content/mom6.mp4"
2. Edit the path to .pkl model -> CHECKPOINT_FILE_PATH: /content/SLOWFAST_32x2_R101_50_50.pkl
3. Edit the path to .json -> LABEL_FILE_PATH: "/content/ava_action_list.json"


```
python3 tools/run_net.py --cfg myconfig/SLOWFAST_32x2_R101_50_50.yaml
```

