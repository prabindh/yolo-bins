**How to test**

The TK1 builds can be tested with the below command.

Dependencies:
- Darknet sources from https://github.com/prabindh/darknet
- v2 Weight file from https://github.com/leetenki/YOLOtiny_v2_chainer/blob/master/tiny-yolo-voc.weights, or from other sources.

Command:
./darknet-cpp detector test cfg/voc.data cfg/tiny-yolo-voc.cfg ../../tiny-yolo-voc.weights