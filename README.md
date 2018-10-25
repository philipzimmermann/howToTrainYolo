# trainYolo
Stuff to prepare for training object detection

-BBoxLabelTool for labeling images: https://github.com/puzzledqs/BBox-Label-Tool

-training images with labels: https://timebutt.github.io/content/other/NFPA_dataset.zip

-clone https://github.com/AlexeyAB/darknet  
-make (GPU=1) (CUDNN=1) (for GPU and CUDA Support)  
-mkdir data/obj  
-add yolo-obj.cfg to cfg folder  (adjust batch, subdivisions, classes, filters)  
-add obj.names to cfg  (adjust object names)  
-add obj.data to cfg   (adjust class number)  
-put images .jpg in directory data/obj  
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
cp howToTrainYolo/yolo-obj.cfg howToTrainYolo/obj.names howToTrainYolo/obj.data darknet/data/obj  
cp NFPA\ dataset/* darknet/data/obj  
cp howToTrainYolo/process.py darknet/data/obj  
python2.7 darknet/data/obj/process.py  
cd darknet  
wget https://pjreddie.com/media/files/darknet53.conv.74  
./darknet detector train cfg/obj.data cfg/yolo-obj.cfg darknet53.conv.74  
