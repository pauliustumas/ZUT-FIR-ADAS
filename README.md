# ZUT-FIR-ADAS

[![ZUT-FIR-ADAS](https://img.youtube.com/vi/utqGU2Yt_qM/0.jpg)](https://www.youtube.com/watch?v=utqGU2Yt_qM)

A new thermal dataset for on-road FIR pedestrian detection in severe weather conditions containing CAN bus data.

### Description

Pedestrian detection has never been an easy task for computer vision and automotive industry. Systems like the advanced driver assistance system (ADAS) highly rely on far infrared (FIR) data captured to detect pedestrians at nighttime. The recent development of deep learning-based detectors has proven the excellent results of pedestrian detection in perfect weather conditions. However, it is still unknown what is the performance in adverse weather conditions. In this paper, it is introduced a 16bit thermal data dataset called ZUT (Zachodniopomorski Uniwersytet Technologiczny) having the most extensive variety of fine-grained annotated images captured in 4 biggest European Union countries captured during severe weather conditions. In addition to this, we also provide a synchronized Controller Area Network (CAN) bus data, including driving speed, brake pedal status, and outside temperature for future ADAS system development. Furthermore, we have tested and provided 16-bit depth modifications for Yolov3 deep neural network (DNN) based detector reaching mean Average Precision (mAP) up to 89.1%.

### Instructions: 
Prefix _b - means benchmark, otherwise used for training/testing

 

### Each recording folder contains:

  16BitFrames - 16bit original capture without processing.

  16BitTransformed - 16bit capture with low pass filter applied and scaled to 640x480.

  annotations - annotations and 8bit images made from 16BitTransformed.

  carParams.csv - a CAN details with coresponding frame ID.

  weather.txt - weather information in which the recording was made.

 

Annotations are made in YOLO (You only look once) Darknet format.

### Low pass filter 

To have images without low pass filter applied you should make the following steps:

- Take 16bit images from 16BitFrames folder and open with OpenCV function like: Mat input = imread(<image_full_path>, -1);

- Then use convertTo function like: input.convertTo(output, input.depth(), sc, sh), where output is transformed Mat, sc is scale and sh is shift from carParams.csv file.

- Finally, scale image to 640x480

### Download

You can use two sources for download:
[IEEE Dataport](https://ieee-dataport.org/open-access/zut-fir-adas)

Or from our server:

[Poland.zip (33.32 GB)](http://88.119.191.48/ZUT/Poland.zip)

[Lithuania.zip (16.85 GB)](http://88.119.191.48/ZUT/Lithuania.zip)

[Germany.zip (18.73 GB)](http://88.119.191.48/ZUT/Germany.zip)

[Denmark.zip (26.11 GB)](http://88.119.191.48/ZUT/Denmark.zip)

[Classes.txt](http://88.119.191.48/ZUT/classes.txt)

### Cite our Dataset

@ARTICLE{9044295,
  author={P. {Tumas} and A. {Nowosielski} and A. {Serackis}},
  journal={IEEE Access}, 
  title={Pedestrian Detection in Severe Weather Conditions}, 
  year={2020},
  volume={8},
  number={},
  pages={62775-62784},}
  
  









