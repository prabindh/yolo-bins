![Prediction](https://github.com/prabindh/yolo-bins/blob/master/capacito/prediction-result.png)

# Auto-labelling, Training and Detection of capacitors in a PCB using Yolo-bins in 1 hour

One of the most time consuming tasks in object detection is labelling. 
This post shows how to perform this automatically and complete the detection task in under an hour of work, for a 3-class model.

## Platform:
Windows 10, x64
CPU: Core i7 Desktop
GPU: Titan GV100
Driver: 421.65
Binaries built with vs2017

## Step1: Installation of CUDA + CUDNN:
- Download CUDA10.0 (not 10.1) from the archives, for ex from [https://developer.nvidia.com/cuda-10.0-download-archive]
- Download CUDNN for CUDA10.0 from Nvidia website (requires registration)
- Download OpenCV3.4.3 dll from [https://opencv.org/releases.html]
The opencv DLL (opencv_world343.dll) should be placed in the same folder as darknet.exe

## Step2: Auto-object-labelling with Euclidaug: [Time taken - 1 minute]
`(Update PATH-TO with the full path to the folder)`

`cd <PATH-TO>yolo-bins\capacito\labelling`

`(Python 3.6.5 + required)`

`pip install -r requirements.txt`

`python euclidaug.py <PATH-TO>yolo-bins\capacito\labelling\pcb-objects <PATH-TO>yolo-bins\capacito\labelling\pcb-bg <PATH-TO>yolo-bins\capacito\labelling\capacitor-train.txt`

`copy out_labels\*.txt out_images\`

`copy capacitor-train.txt ..\capacitor1\capacitor-train.txt`

## Step3: Training to generate the model: [Time taken - 1 hour]
`cd <PATH-TO>yolo-bins\capacito\`

`darknet.exe detector train capacitor1/3class.data capacitor1/yolov2.cfg darknet19_448.conv.23`

The default configuration generates a model file every 1000 iterations. For this run, 4000 iterations are found to be sufficient, hence capacitor1/backup/yolov2_4000.weights file is used. Training can be stopped after this. It takes less than an hour on a GV100 GPU.

Sample logs from last 4k run is below:

   4259: 0.034688, 0.045240 avg loss, 0.001000 rate, 0.923000 seconds, 272576 images

Loaded: 0.000000 seconds

Region Avg IOU: 0.872156, Class: 0.999678, Obj: 0.859775, No Obj: 0.001831, Avg Recall: 1.000000,  count: 11

Region Avg IOU: 0.893025, Class: 0.999848, Obj: 0.894722, No Obj: 0.002967, Avg Recall: 1.000000,  count: 21

Region Avg IOU: 0.882104, Class: 0.999865, Obj: 0.876788, No Obj: 0.002106, Avg Recall: 1.000000,  count: 14

Region Avg IOU: 0.884084, Class: 0.994404, Obj: 0.880232, No Obj: 0.002664, Avg Recall: 1.000000,  count: 14

Region Avg IOU: 0.874172, Class: 0.999808, Obj: 0.863881, No Obj: 0.001964, Avg Recall: 1.000000,  count: 15

Region Avg IOU: 0.924797, Class: 0.999988, Obj: 0.920336, No Obj: 0.001657, Avg Recall: 1.000000,  count: 11

Region Avg IOU: 0.865205, Class: 0.999760, Obj: 0.869471, No Obj: 0.002225, Avg Recall: 1.000000,  count: 16

Region Avg IOU: 0.880660, Class: 0.999920, Obj: 0.885521, No Obj: 0.002014, Avg Recall: 1.000000,  count: 15

If unable to allocate CUDA memory, the field "subdivisions=16" can be increased in multiples of 2 (upto 64)

## Step4: Testing - Predicting the classes:

`darknet.exe detector test capacitor1/3class.data capacitor1/yolov2.cfg capacitor1/backup/yolov2_4000.weights capacitor1/TEST/TEST-CAP2.jpg`

<...>
Loading weights from capacitor1/backup/yolov2_4000.weights...
 seen 64
Done!

capacitor1/TEST/TEST-CAP2.jpg: Predicted in 6.786000 milli-seconds.

cap1: 82%

cap1: 87%

cap1: 91%

cap1: 86%

This test-image is not a part of the training set, and thus shows some amount of generalisation.

### Sources
euclidaug - Can be obtained from https://github.com/prabindh/euclid

darknet - Can be obtained from https://github.com/AlexeyAB/darknet

### Other references for comparison

"A PCB Dataset for Defects Detection and Classification", Weibo Huang, Peng Wei, 2019, https://arxiv.org/pdf/1901.08204.pdf

"[OpenR8 solution] Image_PCB_DefectDetection_SSD512_Caffe (Using deep learning Caffe framework and SSD 512 algorithm for defect detection on PCB)", https://www.openrobot.club/article/index?sn=11178

"Capacitor Detection in PCB Using YOLO Algorithm", Yih-Lon Lin ; Yu-Min Chiang ; Hsiang-Chen Hsu, 2018,
https://ieeexplore.ieee.org/document/8520170/
