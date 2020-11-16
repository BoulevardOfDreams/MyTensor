# MyTensor
I have perform transfer learning from SSD_Inception_v2 coco model. My objective is to create a new model which is made light weight and able to run on raspberrypi.

In this learning journey, i have been following guides from <br>
https://github.com/tensorflow/models/blob/master/research/object_detection

I have converted this model to tflite file and run it on an mobile application.

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
batch_size  = 12
num_classes = 1
num_steps   = 2000

# Results of detection
![result1](https://user-images.githubusercontent.com/42071698/99287169-de8c8300-2874-11eb-823c-c2699d615ddb.JPG)
![result2](https://user-images.githubusercontent.com/42071698/99287184-e4826400-2874-11eb-8161-80694b1c19b9.JPG)
![result3](https://user-images.githubusercontent.com/42071698/99287191-e64c2780-2874-11eb-96aa-e26c61ccdbcf.JPG)
![result4](https://user-images.githubusercontent.com/42071698/99287194-e77d5480-2874-11eb-8e21-8ebbe4e6c2c6.JPG)
![result5](https://user-images.githubusercontent.com/42071698/99287197-e8ae8180-2874-11eb-8f3b-1461a91ba5ad.JPG)
