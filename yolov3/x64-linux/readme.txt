Covers both arapaho and darknet-cpp.

Copy yolov3.weights from https://pjreddie.com/media/files/yolov3.weights

1. For arapaho build, just run ./arapaho in this folder, as the input files are stored.

Rename yolov3.weights to input.weights.

Loading weights from input.weights...Done!
Warning: Read classes from cfg (80) > maxClasses (2)
==> Detected [3] objects in [0.343209] seconds
cap.read failed/EoF - AV file input.jpg


2. For darknet-cpp, follow below steps.

./darknet-cpp detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
layer     filters    size              input                output
0 conv     32  3 x 3 / 1   256 x 256 x   3   ->   256 x 256 x  32  0.113 BFLOPs
1 conv     64  3 x 3 / 2   256 x 256 x  32   ->   128 x 128 x  64  0.604 BFLOPs
2 conv     32  1 x 1 / 1   128 x 128 x  64   ->   128 x 128 x  32  0.067 BFLOPs
3 conv     64  3 x 3 / 1   128 x 128 x  32   ->   128 x 128 x  64  0.604 BFLOPs
4 res    1                 128 x 128 x  64   ->   128 x 128 x  64
5 conv    128  3 x 3 / 2   128 x 128 x  64   ->    64 x  64 x 128  0.604 BFLOPs
6 conv     64  1 x 1 / 1    64 x  64 x 128   ->    64 x  64 x  64  0.067 BFLOPs
7 conv    128  3 x 3 / 1    64 x  64 x  64   ->    64 x  64 x 128  0.604 BFLOPs
8 res    5                  64 x  64 x 128   ->    64 x  64 x 128
9 conv     64  1 x 1 / 1    64 x  64 x 128   ->    64 x  64 x  64  0.067 BFLOPs
10 conv    128  3 x 3 / 1    64 x  64 x  64   ->    64 x  64 x 128  0.604 BFLOPs
11 res    8                  64 x  64 x 128   ->    64 x  64 x 128
12 conv    256  3 x 3 / 2    64 x  64 x 128   ->    32 x  32 x 256  0.604 BFLOPs
13 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
14 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
15 res   12                  32 x  32 x 256   ->    32 x  32 x 256
16 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
17 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
18 res   15                  32 x  32 x 256   ->    32 x  32 x 256
19 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
20 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
21 res   18                  32 x  32 x 256   ->    32 x  32 x 256
22 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
23 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
24 res   21                  32 x  32 x 256   ->    32 x  32 x 256
25 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
26 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
27 res   24                  32 x  32 x 256   ->    32 x  32 x 256
28 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
29 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
30 res   27                  32 x  32 x 256   ->    32 x  32 x 256
31 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
32 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
33 res   30                  32 x  32 x 256   ->    32 x  32 x 256
34 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
35 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
36 res   33                  32 x  32 x 256   ->    32 x  32 x 256
37 conv    512  3 x 3 / 2    32 x  32 x 256   ->    16 x  16 x 512  0.604 BFLOPs
38 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
39 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
40 res   37                  16 x  16 x 512   ->    16 x  16 x 512
41 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
42 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
43 res   40                  16 x  16 x 512   ->    16 x  16 x 512
44 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
45 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
46 res   43                  16 x  16 x 512   ->    16 x  16 x 512
47 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
48 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
49 res   46                  16 x  16 x 512   ->    16 x  16 x 512
50 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
51 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
52 res   49                  16 x  16 x 512   ->    16 x  16 x 512
53 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
54 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
55 res   52                  16 x  16 x 512   ->    16 x  16 x 512
56 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
57 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
58 res   55                  16 x  16 x 512   ->    16 x  16 x 512
59 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
60 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
61 res   58                  16 x  16 x 512   ->    16 x  16 x 512
62 conv   1024  3 x 3 / 2    16 x  16 x 512   ->     8 x   8 x1024  0.604 BFLOPs
63 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
64 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
65 res   62                   8 x   8 x1024   ->     8 x   8 x1024
66 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
67 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
68 res   65                   8 x   8 x1024   ->     8 x   8 x1024
69 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
70 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
71 res   68                   8 x   8 x1024   ->     8 x   8 x1024
72 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
73 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
74 res   71                   8 x   8 x1024   ->     8 x   8 x1024
75 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
76 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
77 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
78 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
79 conv    512  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 512  0.067 BFLOPs
80 conv   1024  3 x 3 / 1     8 x   8 x 512   ->     8 x   8 x1024  0.604 BFLOPs
81 conv    255  1 x 1 / 1     8 x   8 x1024   ->     8 x   8 x 255  0.033 BFLOPs
82 detection
83 route  79
84 conv    256  1 x 1 / 1     8 x   8 x 512   ->     8 x   8 x 256  0.017 BFLOPs
85 upsample            2x     8 x   8 x 256   ->    16 x  16 x 256
86 route  85 61
87 conv    256  1 x 1 / 1    16 x  16 x 768   ->    16 x  16 x 256  0.101 BFLOPs
88 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
89 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
90 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
91 conv    256  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 256  0.067 BFLOPs
92 conv    512  3 x 3 / 1    16 x  16 x 256   ->    16 x  16 x 512  0.604 BFLOPs
93 conv    255  1 x 1 / 1    16 x  16 x 512   ->    16 x  16 x 255  0.067 BFLOPs
94 detection
95 route  91
96 conv    128  1 x 1 / 1    16 x  16 x 256   ->    16 x  16 x 128  0.017 BFLOPs
97 upsample            2x    16 x  16 x 128   ->    32 x  32 x 128
98 route  97 36
99 conv    128  1 x 1 / 1    32 x  32 x 384   ->    32 x  32 x 128  0.101 BFLOPs
100 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
101 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
102 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
103 conv    128  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 128  0.067 BFLOPs
104 conv    256  3 x 3 / 1    32 x  32 x 128   ->    32 x  32 x 256  0.604 BFLOPs
105 conv    255  1 x 1 / 1    32 x  32 x 256   ->    32 x  32 x 255  0.134 BFLOPs
106 detection
Loading weights from yolov3.weights...Done!
data/dog.jpg: Predicted in 0.066842 seconds.
dog: 100%
truck: 51%
car: 77%
bicycle: 74%