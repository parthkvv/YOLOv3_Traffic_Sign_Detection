- Python3
- [Yolov3](https://github.com/pjreddie/darknet)


### Preparing Dataset 

All the image files will reside in multiple folders. Copy or move all the images from different folders to one single folder.
Create a new folder under ```rgb/train``` and rename it as ```rgb/train/traffic_light_images```.  

Move the yolov3-tiny-bosch.cfg from the \config folder to the same (traffic_lights) folder. Mae sure there are following files in the traffic_lights folder.
  - train.txt
  - test.txt
  - bosch.data
  - bosch.names
  - yolov3-tiny-bosch.cfg
  - backup folder which stores the weights

Download the yolov3 imagenet darknet53 [weights](https://pjreddie.com/darknet/yolo/)
Run the following on terminal for training the model
  ```
  cd darknet
  ./darknet detector train traffic_lights/bosch.data traffic_lights/yolov3-tiny-bosch.cfg darknet53.conv.74
  ```

### Testing

cd darknet
./darknet detector demo traffic_lights/bosch.data traffic_lights/yolov3-tiny-bosch.cfg traffic_lights/backup/<weight_file> <video file>

Actual testing was done on OpenImageV6 images.
