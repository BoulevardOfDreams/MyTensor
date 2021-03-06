# MyTensor
I have perform transfer learning from SSD_Inception_v2 coco model.<br>

My objective is use custom dataset from OpenImage to create a custom model for my own used.<br>

I have used custom dataset downloaded from OpenImage for training.<br>

# Train environment and model details
Version:<br>
Tensorflow version 1.x

Github repository:<br>
https://github.com/tensorflow/models.git

Dataset source:<br>
Google open image<br>
https://storage.googleapis.com/openimages/web/index.html

Training Object:<br>
Human Body 

Train label/Test label:<br>
oid_to_pascal_voc_xml.py

Model:<br>
SSD_Inception_v2 (from model zoo)

Config file:<br>
ssd_inception_v2_coco.config

Parameter:<br>
batch_size  = 32
num_classes = 1
num_steps   = 2000
<br>

# Graphs and Histogram (From Tensorboard)
Due to time constraint, I have set the training steps to around 1512 steps (7 hour 16 mins)

**Learning Rate**
![LearningRate](https://user-images.githubusercontent.com/42071698/99879266-b28f4a00-2c46-11eb-8ecb-181a09fbb854.JPG)

**Loss/Steps**
![TotalLoss](https://user-images.githubusercontent.com/42071698/99879221-5298a380-2c46-11eb-9210-e081a93473a8.JPG)

# Results of detection
![result1](https://user-images.githubusercontent.com/42071698/99287169-de8c8300-2874-11eb-823c-c2699d615ddb.JPG)
![result2](https://user-images.githubusercontent.com/42071698/99287184-e4826400-2874-11eb-8161-80694b1c19b9.JPG)
![result3](https://user-images.githubusercontent.com/42071698/99287191-e64c2780-2874-11eb-96aa-e26c61ccdbcf.JPG)
![result4](https://user-images.githubusercontent.com/42071698/99287194-e77d5480-2874-11eb-8e21-8ebbe4e6c2c6.JPG)
![result5](https://user-images.githubusercontent.com/42071698/99287197-e8ae8180-2874-11eb-8f3b-1461a91ba5ad.JPG)

# Steps
1.) <br>
I have chosen human body as my custom datasets.<br>
All the custom image label and xml are produced and uploaded to Google Drive.<br>

 2.)<br>
**Run xml_to_csv.py**:<br>
Generate train and test dataset CSV.<br>

**Run generate_tfrecord.py:**<br>
This CSV is used to generate tensorflow record afterwards (TFRecord)<br>
<br>
Note: tfrecord files are binary that are optimized for faster processing, not human       readable.<br>

**Generate labelmap.pbtxt**<br>
This shows number of class to be trained. (Currently, only 1 class : human body)<br>

3.)
**Download SSD_inception_v2.config**<br>
Adding Train and test record file generated previously.

**Configure as follows:**<br>
batch_size  = 12<br>
num_classes = 1<br>
num_steps   = 2000<br>

4.)
**Run the training**<br>
<br>

Two files above can be found in link below:<br>
https://github.com/BoulevardOfDreams/object_detection_demo

In this learning journey, i have been following guides from <br>
https://github.com/tensorflow/models/blob/master/research/object_detection

I have converted this model to tflite file and run it on an mobile application.
