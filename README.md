# Plate Detection

## Introduction
This is a yolov7 model that is fine-tuned to detect plates and recognize the plate from image or video.

<br>

## Datasets
I used the [Iranian plate dataset](https://github.com/SeyedHamidreza/car_plate_dataset) and added to the [roboflow license plate object detection datasets](https://public.roboflow.com/object-detection/license-plates-us-eu). I used preprocessing and data augmentation such as blur and rotation.

<br>

## Training
Training notebook (Plate_Detection_Yolov7.ipynb) is in src directory the training result was very good and reached around ~ 0.85 mAP.

### Confusion Matrix:
![image](./yolo_training_results/confusion_matrix.png)

### F1_curve:
![image2](./yolo_training_results/F1_curve.png)

### R_curve:
![image3](./yolo_training_results/R_curve.png)

### Whole result
![image4](./yolo_training_results/results.png)

<br>

## Prediction
I put 11 images in the test set to evaluate the object detection model.
* The car label means plate license

![](./yolo_training_results/test_set/1.jpg)
![](./yolo_training_results/test_set/2.jpg)
![](./yolo_training_results/test_set/3.jpg)
![](./yolo_training_results/test_set/4.jpg)
![](./yolo_training_results/test_set/5.jpg)

See the test_set folder for more images...

<br>

## Plate Recognition
After license plate localization, I tested 3 images for cropping and detecting the plates. The results are in plate_inference directory and named by the plate text.

### images:

![](./test/pelakir_2.jpg)
![](./test/pelakir_1.jpg)
![](./test/pelak.jpeg)

<br>

### Results:

![](./plate_inference/%D8%B7%D8%A7.png)

![](./plate_inference/%D9%A2%D9%A4%D9%A7%D9%A9%D9%A9%D9%89%D9%A7%D9%A8.png)

![](./plate_inference/%D9%A8%D9%A1%209%20%D9%A6%D9%A3%20%D9%A6%D9%A3%D9%A8.png)

<br>

## Usage 
For using the plate cropping and ocr you should install the packages in requirements.txt and run by the following command:

```
python src/yolov7/plate_ocr.py
```