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

# menthod used
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
Li, Mi = SGN(I, Pi) Pi ∈ I
# Method used for video Splicing
In Our model resnext50 are used for feature extraction 
from face cropped videos followed by one layer of 
LSTM. The data loader splits the whole face cropped 
videos dataset into training and testing set in form of 
minibatch.
3.4.1 Extraction of Feature from ResNext:
We are using resnext50 for detecting and extracting the 
frame level feature from videos. For fine tuning we are 
using one extra layer and select a proper learning rate.

