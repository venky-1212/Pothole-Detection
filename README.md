# Attention Aggregation Framework




## Setup
Please setup the Pothole-600 Dataset and pretrained weights according to the following folder structure:
```
AAFramework
 |-- checkpoints
 |-- data
 |-- datasets
 |  |-- pothole600
 |-- models
 ...
```
The Pothole-600 Dataset `pothole600` can be downloaded from [here](https://sites.google.com/view/pothole-600/dataset?authuser=0), and the pretrained weights `checkpoints` for our AA-UNet and AA-RTFNet can be downloaded from [here](https://drive.google.com/file/d/1yzJf1bFZxvS8bo35MYscRnc807_h0Kjg/view?usp=sharing).


## Usage

### Testing on the Pothole-600 Dataset
For testing, you need to setup the `checkpoints` and the `datasets/pothole600` folder as mentioned above. Then, run the following script:
```
bash ./scripts/test_aaunet_rgb.sh
bash ./scripts/test_aaunet_tdisp.sh
bash ./scripts/test_aartfnet.sh
```
for testing AA-UNet with input RGB, AA-UNet with input T-Disp and AA-RTFNet with input RGB and T-Disp, respectively.
and you will get the prediction results in `testresults`.

If everything works fine, you will get an IoU score of 51.4, 70.1 and 73.8 for AA-UNet with input RGB, AA-UNet with input T-Disp and AA-RTFNet with input RGB and T-Disp, respectively, as reported in the paper.

### Training on the Pothole-600 Dataset
For training, you need to setup the `datasets/pothole600` folder as mentioned above. Then, run the following script:
```
bash ./scripts/train_aaunet_rgb.sh
bash ./scripts/train_aaunet_tdisp.sh
bash ./scripts/train_aartfnet.sh
```
for training AA-UNet with input RGB, AA-UNet with input T-Disp and AA-RTFNet with input RGB and T-Disp, respectively. The weights will be saved in `checkpoints` and the tensorboard record containing the loss curves as well as the performance on the validation set will be saved in `runs`.



## Citation
If you use this code for your research, please cite our paper.
```
@inproceedings{fan2020we,
  title        = {We learn better road pothole detection: From attention aggregation to adversarial domain adaptation},
  author       = {Fan, Rui and Wang, Hengli and Bocus, Mohammud J and Liu, Ming},
  booktitle    = {European Conference on Computer Vision},
  pages        = {285--300},
  year         = {2020},
  organization = {Springer}
}
```


