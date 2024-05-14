# Mowito
Given template images of the object of interest, finding the object in the test image and the rotation between the object in the template image and the object in the test images

## How To Run
open the mowito.ipynb file and run the first 4 cells

in the 4th cell edit the image name variables to your image dir, you will get the rotation angle as text output in console

for image output, uncomment the cv2.imwrite line and add your output dir

for the bounding box around the object, run the 2 cells with yolo code in them, edit the image dir

use the cropped images obtained from yolo model in the rotation function for better accuracy

## Summary Of Work
### Methodology
finding transation of object in image and finding the rotation value of object are treated as two seperate tasks for simplicity and speed

the location of object is found using yolov8 segmentation model, this model gives the bounding box around the object, cropped image as well as a detailed segmented object
this model was used with the purpose of covering all real world applications and complexities of this task

after obtaining the cropped versions of template and test images, they are passed to the "rotation" function
this function utilizes the inbuilt functions found in OpenCV library that can determine the rotation of object in given images using keypoints and matching them

### Reasoning behind used techniques
for the task of locating the object and finding the translation values, yolo object detection and segmentation models are most suitable due to their high accuracy and usability
due to lack of training data and scope of this task, only the pretrained model was used but in the case of real world application a custom trained yolo model can be made to cover all nuances that this task simplifies

after research it was determined that the inbuilt functions in OpenCV are the most elegant solution to the problem, other similar approaches also utilize the same concept of matching keypoints and underlying code for them is the same

### Testing
along with using the test images provided, a custom image was used for giving a conclusive proof on accuracy of the solution
the image was rotated 1 deg artifically and the 360 images obtained this way were passed through the rotation function
this test gives highly promissing results which can be seen in the mowito.ipynb file cell outputs as well as the custom image output folder
