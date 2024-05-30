# license-plate-detection-and-recognition

# License Plate Detection
Dataset used - [License Plate Recognition Image Dataset](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e/dataset/4)

YOLOv8 is trained on the above mentioned dataset to detect the license plates.

Some of the outputs from the license plate detector model (YOLOv8) are as follows:


![val_batch1_pred](https://github.com/Parekh03/license-plate-detection-and-recognition/assets/110220047/d3858f6a-6cb7-4029-8f68-7d520b0e76ef)

# License Plate Recognition and Detection for images

## Steps involved:
1. Read the images using OpenCV
2. Detect the license plate using license plate detector model (YOLOV8)
3. Get the position/coordinates of the license plate in the image
4. Crop the original image using the coordinates of the license plate
5. Perform thresholding of the cropped license plate image
6. Extract the text from the license plate using EasyOCR
7. Draw the bounding box representing the detected text, over the original image
8. Save or display the annotated image

Dataset used for detection and recognition: [Indian Vehicle Dataset](https://www.kaggle.com/datasets/saisirishan/indian-vehicle-dataset)

Some of the outputs obtained by performing the above mentioned steps are:

![BeFunky-collage](https://github.com/Parekh03/license-plate-detection-and-recognition/assets/110220047/35fbb1ae-6c75-48e5-a748-5305e6d17254)



![BeFunky-collage (2)](https://github.com/Parekh03/license-plate-detection-and-recognition/assets/110220047/0cebd55f-88e5-4f08-ae24-6dbfdaad6a3d)




# License plate detection and recognition for video

Steps involved:
1. Read each frame of the video using OpenCV
2. Detect the car/cars in the frame using a pre-trained YOLOv8 model.
3. Filter out the non-vehicle detections. (Only car, motorcycle, bus and truck to be considered)
4. Track vehicles using [SORT](https://github.com/abewley/sort) algorithm
5. Detect license plates in that frame using the trained license plate detector model (YOLOv8)
6. Assign a license plate to each car
7. Get the position/coordinates of the license plates and crop them accordingly
8. Perform grayscaling and thresholding of the cropped license plates
9. Draw bounding boxes representing the detected texts
10. Perform step 1 to 8 for all the frames of the video
11. Save the annotated video

![output_video_2 - Trim (5)](https://github.com/Parekh03/license-plate-detection-and-recognition/assets/110220047/3243658d-5258-4184-8ca7-bec224880572)


# Observations
Performing thresholding can sometimes lead to worse results or vice versa. 

In case of images, where each image has different configurations (brightness, contrast, quality, etc), it becomes neccesary to tune/change the thresholding parameters accordingly, to detect the text using EasyOCR. In some of the cases, it was observed that even though thresholding was performed correctly, it led to lower confidence score and incorrect detections.

However, in case of the video used in this project, thresholding has proved to enhance the results and accuracy in detecting the texts from the license plate.

# Showstopppers
1. Quality of the image - Low quality images lead to incorrect text detections from license plates.
2. Font of texts in license plate - Unreadable or unclear texts can cause problems in detecting texts.
3. Brightness, contrast and other configurations
4. Position/angle of images

In such cases, some of the text from the license plate may be incorrectly detected by EasyOCR

Some example outputs in case of the above mentioned showstoppers:

![BeFunky-collage (3)](https://github.com/Parekh03/license-plate-detection-and-recognition/assets/110220047/feec7dd9-f048-4649-8c15-cd6b60dbe058)







