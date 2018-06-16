./darknet-cpp detector test cfg/voc.data cfg/tiny-yolo-voc.cfg ../../tiny-yolo-voc.weights

layer     filters    size              input                output
    0 conv     16  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  16
    1 max          2 x 2 / 2   416 x 416 x  16   ->   208 x 208 x  16
    2 conv     32  3 x 3 / 1   208 x 208 x  16   ->   208 x 208 x  32
    3 max          2 x 2 / 2   208 x 208 x  32   ->   104 x 104 x  32
    4 conv     64  3 x 3 / 1   104 x 104 x  32   ->   104 x 104 x  64
    5 max          2 x 2 / 2   104 x 104 x  64   ->    52 x  52 x  64
    6 conv    128  3 x 3 / 1    52 x  52 x  64   ->    52 x  52 x 128
    7 max          2 x 2 / 2    52 x  52 x 128   ->    26 x  26 x 128
    8 conv    256  3 x 3 / 1    26 x  26 x 128   ->    26 x  26 x 256
    9 max          2 x 2 / 2    26 x  26 x 256   ->    13 x  13 x 256
   10 conv    512  3 x 3 / 1    13 x  13 x 256   ->    13 x  13 x 512
   11 max          2 x 2 / 1    13 x  13 x 512   ->    13 x  13 x 512
   12 conv   1024  3 x 3 / 1    13 x  13 x 512   ->    13 x  13 x1024
   13 conv   1024  3 x 3 / 1    13 x  13 x1024   ->    13 x  13 x1024
   14 conv    125  1 x 1 / 1    13 x  13 x1024   ->    13 x  13 x 125
   15 detection
Setup: net.n = 16
net.layers[0].batch = 8
Loading weights from ../../tiny-yolo-voc.weights...mj = 0, mn = 1, *(net->seen) = 2566400
load_convolutional_weights: l.n*l.c*l.size*l.size = 432
load_convolutional_weights: l.n*l.c*l.size*l.size = 4608
load_convolutional_weights: l.n*l.c*l.size*l.size = 18432
load_convolutional_weights: l.n*l.c*l.size*l.size = 73728
load_convolutional_weights: l.n*l.c*l.size*l.size = 294912
load_convolutional_weights: l.n*l.c*l.size*l.size = 1179648
load_convolutional_weights: l.n*l.c*l.size*l.size = 4718592
load_convolutional_weights: l.n*l.c*l.size*l.size = 9437184
load_convolutional_weights: l.n*l.c*l.size*l.size = 128000
Done!
Enter Image Path:<>dog.jpg
test_detector: layers = 13, 13, 5
dog.jpg: Predicted in 0.012921 seconds.
car: 34%
car: 55%
car: 51%
dog: 78%
bicycle: 35%

