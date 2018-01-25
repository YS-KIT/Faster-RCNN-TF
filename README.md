# Faster-RCNN_TF

This is an experimental Tensorflow implementation of Faster RCNN - it was to apply networks to Logo recongnition.
For details about R-CNN please refer to the paper [Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks](http://arxiv.org/pdf/1506.01497v3.pdf) by Shaoqing Ren, Kaiming He, Ross Girshick, Jian Sun.


### Requirements: software

1. Requirements for Tensorflow (versions of GPU)
(see: [Tensorflow](https://www.tensorflow.org/))

2. Python packages you might not have: `cython`, `python-opencv`, `easydict`.But python must be the version of 2.7.

3. you need to the server have cuda 8.0 already installed.

### Requirements: hardware

1. For training the end-to-end version of Faster R-CNN with VGG16, 3G of GPU memory is sufficient (depending on the size of your data)

### Installation 

1. Clone the Faster R-CNN libraries
   Open the server shell
  # Make sure to clone with --recursive
  git clone --recursive https://github.com/YangShuoys/Faster-RCNN-TF.git
 

2. Build the Cython modules
   Open the server shell
    cd Faster-RCNN-TF/lib
    make
    

### Demo

*After successfully completing lib environment, you'll be ready to run the demo.

our libraries have the model training on Pascal_voc2007(under /tools/model/).
you can use the model directly.

To run the demo

cd Faster-RCNN-TF/tools/
python demo.py --model model_path(/tools/model/model_name)


The demo performs detection using a VGG16 network trained for detection on Pascal_voc2007 of Logo recognition.

### Training 
1. Your need to prepare the training, validation and test data (It must be the Pascal_voc2007 data format) 	 
	

2. Save all of these files into one folder named `VOCdevkit2007`

	

3. It should have this basic structure

      cd Faster-RCNN-TF/
  	$data/VOCdevkit2007/                  # development kit
  	$VOCdevkit2007/VOC2007/               # It consists of three folders: Annotations, ImageSets, JPEGImages


4. You must revise the target class
  	

    
5. Our net weights stores at this location
  
      /tools/model/
   

6. Run script to train and test model
	
	cd Faster-RCNN-TF/
	./experiments/scripts/faster_rcnn_end2end.sh $DEVICE $DEVICE_ID VGG16 pascal_voc
	
  DEVICE is either cpu/gpu

### The result of testing on Pascal_voc2007 of Logo recognition

| Classes       | AP     |
|-------------|--------|
| 0001        | 0.7027 |
| 0002        | 0.8661 |
| 0003        | 0.8606 |
         ，
         ，
         ，
         ，
| 0028        | 0.8838 |
| 0029        | 0.6321 |
| 0030        | 0.7064 |
| Mean AP     | 0.7915 |




