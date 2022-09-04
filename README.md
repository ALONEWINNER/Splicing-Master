# Splicing-Master
#Image splicing
is a prominent method of digital image 
manipulation. The term "image splicing" refers to the 
cutting and pasting of a specific region of a donor image 
into the host image. Spliced region identification has a long 
history in digital picture forensics.
![Libray Management App - Flask](https://github.com/ALONEWINNER/Splicing-Master/blob/main/download.png)
#video Splicing
The volume of image data generated in the last decade has 
exploded thanks to the emergence of social networking 
platforms like Facebook, Telegram, and Instagram. For
internet companies like Facebook, the use of image (and 
video) editing software like Adobe Photoshop to make 
doctored photographs and films is a major worry. These 
photos are common sources of fake news and are frequently 
utilized in unethical ways, such as encouraging mobs. We 
must establish the authenticity of a problematic photograph 
before taking action based on it. Image forgery can be 
problematic in a variety of situations.
![Libray Management App - Flask](https://github.com/ALONEWINNER/Splicing-Master/blob/main/vedio_spliced%20region.jpg)
# Dataset used:
We are using Columbia[1] dataset. In this dataset, there 
are two folder, first folder(4cam_auth) contains authentic 
images, and second folder(4cam_splc) contains spliced 
images. By the term 'authentic', we mean an image that is 
taken using single camera. The 4cam_auth folder contains 
183 images and in 4cam_splc, there are 180.
# For Video Splicing 
We are using a mixed dataset which consists of equal 
amount of videos from different dataset sources like 
YouTube, FaceForensics++[26], Video Splicing detection 
challenge dataset[25](see Figure ). Our newly prepared 
dataset contains 50% of the original video and 50% of the 
manipulated Video Splicing videos. The dataset is split
into 70% train and 30% test.

#menthod used
3.3 Model For Image Splicing
We designed our model in two parts for the detection of 
the image integration region. The first is the training and 
the second is the post-processing part. In the training 
network, let a candidate image be I and Non-overlapping 
patch sets Ip, and the goal of our model is to detect
whether each patch has been added (also called patch 
classification) and which pixels it is in. patch Pi((Pi ∈ Ip) 
belongs to the patched region (also called patch 
segmentation).So mathematically it is written as -
Li, Mi = SGN(I, Pi) Pi ∈ Ip
Where Li is the label of current patch Pi, and Mi is the 
segmentation results of the spliced region.
Combining the global image and local patching in our 
model is used in our framework for network classification 
and post processing. In the post-processing stage, CRF is 
used to link color and position. After that, we just use the 
resulting segmentation mask output as the single 
probability of the CRF. Therefore, the input image's suffix 
mask Mpp can be written as:
Mpp = CRF(I, M)
Where M= ∑ i ∈ Ip Mi is the output segmentation 
probability mask of semi global network.
3.3.1 Semi-Global Network:
It is divided into two part one is used for extraction of 
global features and second part is used for extraction of 
features from patches on two different networks. They are 
trained synchronously by ground truth level and ground 
truth mask.
3.3.2 Network for extraction features from patches:
As shown in Fig. 3, This netwok is used for feature 
extraction for patches. The input of this network is non 
overlapping patches from original image .it is used for 
classification and segmentation. In this type of 
classification, a block of size 64x64 is given as input to 
CNN. CNN with 2 layers is used for extracting two 
dimensional low-level feature map is divided into 8x8 
blocks. For establishing relationship between pixel of 
network block LSTM are used. 
3.3.3 Network for extraction of Global features:
This network is used for extracting of global features like 
as light shadow background from Input image.
For this ResNet50 is added. Now the output of LSTM is 
used for classification of image and for reconstruction of 
two dimensional feature map. Now the output of LSTM 
are blocks. These blocks are reshaped .2 layer of CNN is 
applied and at the end of network Softmax is applied.
3.4 Model for Video Splicing
In Our model resnext50 are used for feature extraction 
from face cropped videos followed by one layer of 
LSTM. The data loader splits the whole face cropped 
videos dataset into training and testing set in form of 
minibatch.
3.4.1 Extraction of Feature from ResNext:
We are using resnext50 for detecting and extracting the 
frame level feature from videos. For fine tuning we are 
using one extra layer and select a proper learning rate.

