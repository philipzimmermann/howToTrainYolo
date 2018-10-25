# trainYolo
Stuff to prepare for training object detection

-BBoxLabelTool for labeling images

-training images with labels: https://timebutt.github.io/content/other/NFPA_dataset.zip

-clone https://github.com/AlexeyAB/darknet
-make (GPU=1) (CUDNN=1) (for GPU and CUDA Support)
-add yolo-obj.cfg to cfg folder  (adjust batch, subdivisions, classes, filters)
-add obj.names to build/darknet/x64/data\  (adjust object names)
-add obj.data to build\darknet\x64\data\   (adjust class number)
-put images .jpg in directory build\darknet\x64\data\obj\
-add labels to build\darknet\x64\data\obj\
-run process.py to create train.txt and test.txt
wget https://pjreddie.com/media/files/darknet53.conv.74 (to build\darknet\x64)
-start training: darknet.exe detector train data/obj.data yolo-obj.cfg darknet53.conv.74
-result is located in build\darknet\x64\backup\

