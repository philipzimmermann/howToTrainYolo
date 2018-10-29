# trainYolo
Stuff to prepare for training object detection
(Set burnin to 0 for training rate to start high)

-BBoxLabelTool for labeling images: https://github.com/puzzledqs/BBox-Label-Tool

-training images with labels: https://timebutt.github.io/content/other/NFPA_dataset.zip

-clone https://github.com/AlexeyAB/darknet  
-make (GPU=1) (CUDNN=1) (for GPU and CUDA Support)  
-mkdir data/obj  
-copy yolo-obj.cfg to cfg folder  (adjust batch, subdivisions, classes, filters) (It's the yolo v3 config with changes)  
-copy obj.names to cfg  (adjust object names)  
-copy obj.data to cfg   (adjust class number)  
-put .jpg images in directory data/obj  
-add labels to data/obj/  
-(convert labels? https://github.com/Guanghan/darknet/blob/master/scripts/convert.py)  
-run process.py in obj/data folder to create train.txt and test.txt  
wget https://pjreddie.com/media/files/darknet53.conv.74 (to darknet/)  
-start training: ./darknet detector train cfg/obj.data cfg/yolo-obj.cfg darknet53.conv.74  
-result is located in backup?


shell:  

git clone https://github.com/phixxx5/howToTrainYolo  
wget https://timebutt.github.io/content/other/NFPA_dataset.zip  
unzip NFPA_dataset.zip  
git clone https://github.com/AlexeyAB/darknet  
cd darknet  
make  
mkdir data/obj  
cd ..  
cp howToTrainYolo/yolo-obj.cfg howToTrainYolo/obj.names howToTrainYolo/obj.data darknet/cfg/  
cp NFPA\ dataset/* darknet/data/obj  
cp howToTrainYolo/process.py darknet/data/obj  
cd darknet  
python2.7 data/obj/process.py  
wget https://pjreddie.com/media/files/darknet53.conv.74  
./darknet detector train cfg/obj.data cfg/yolo-obj.cfg darknet53.conv.74  
