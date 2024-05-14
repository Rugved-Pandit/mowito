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

## Outputs
### Example 1
#### template
![screenshot_2024-05-02_17-12-17](https://github.com/Rugved-Pandit/mowito/assets/62091349/33b71d3b-2c3f-4529-8264-c23f2f447fca)
![screenshot_2024-05-02_17-12-17](https://github.com/Rugved-Pandit/mowito/assets/62091349/ad9f35d5-3b77-417b-9c6b-174385d8bf4e)
#### test
![screenshot_2024-05-02_17-18-41](https://github.com/Rugved-Pandit/mowito/assets/62091349/532ccc49-dc9d-47da-b787-a27c268615d9)
![screenshot_2024-05-02_17-18-41](https://github.com/Rugved-Pandit/mowito/assets/62091349/1aac90e1-39e9-4f67-a2cc-34302d12be8e)
![screenshot_2024-05-02_17-18-41](https://github.com/Rugved-Pandit/mowito/assets/62091349/69872556-9b78-49a1-9920-6fec618b2075)

### Example 2
#### template
![screenshot_2024-05-02_17-18-27](https://github.com/Rugved-Pandit/mowito/assets/62091349/1ba9df1a-510b-4a3f-b07f-37ec723f46a4)
![screenshot_2024-05-02_17-18-27](https://github.com/Rugved-Pandit/mowito/assets/62091349/a0e4e3a6-8243-4597-b3ae-7e1a025be0a2)
#### test
![screenshot_2024-05-02_17-23-01](https://github.com/Rugved-Pandit/mowito/assets/62091349/a666ad88-51a5-450c-bc3f-c77a5f0665e9)
![screenshot_2024-05-02_17-23-01](https://github.com/Rugved-Pandit/mowito/assets/62091349/dde59b1e-fbda-4314-98d7-558102338f2e)
![screenshot_2024-05-02_17-23-01](https://github.com/Rugved-Pandit/mowito/assets/62091349/8093db95-57ec-482d-bf2a-6e9ce39991da)

### Example 3
#### template
![screenshot_2024-05-02_17-18-27](https://github.com/Rugved-Pandit/mowito/assets/62091349/1ba9df1a-510b-4a3f-b07f-37ec723f46a4)
![screenshot_2024-05-02_17-18-27](https://github.com/Rugved-Pandit/mowito/assets/62091349/a0e4e3a6-8243-4597-b3ae-7e1a025be0a2)
#### test
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/cbb67cec-e0a6-4bd9-b196-01dd52fc04c5)
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/7e6add4b-44b5-4400-8e1a-9d7e8d39cb99)
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/f7ed14ad-83d3-4529-93ee-962e2de2065f)


### Example 4
#### template
![screenshot_2024-05-02_17-22-50](https://github.com/Rugved-Pandit/mowito/assets/62091349/a03b19e4-2bf6-497e-99a0-c4cde92f2ab4)
![screenshot_2024-05-02_17-22-50](https://github.com/Rugved-Pandit/mowito/assets/62091349/95317b88-2d9f-47e1-a7a0-07ebf04d4261)
#### test
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/a2d9e865-25a1-4a89-877f-330943c7a0a7)
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/9d6cccb7-db65-472d-a27f-5f4f3120dcf0)
![screenshot_2024-05-02_17-23-09](https://github.com/Rugved-Pandit/mowito/assets/62091349/abe80543-f997-4498-85bc-6225f110b682)

### Example 5
#### template
![screenshot_2024-05-02_17-22-50](https://github.com/Rugved-Pandit/mowito/assets/62091349/a03b19e4-2bf6-497e-99a0-c4cde92f2ab4)
![screenshot_2024-05-02_17-22-50](https://github.com/Rugved-Pandit/mowito/assets/62091349/95317b88-2d9f-47e1-a7a0-07ebf04d4261)
#### test
![screenshot_2024-05-02_17-23-22](https://github.com/Rugved-Pandit/mowito/assets/62091349/43de648c-ff2e-4faf-8b47-145dc2412b10)
![screenshot_2024-05-02_17-23-22](https://github.com/Rugved-Pandit/mowito/assets/62091349/a5eb1a83-f0b3-49fa-8308-463196fec440)
![screenshot_2024-05-02_17-23-22](https://github.com/Rugved-Pandit/mowito/assets/62091349/0afa914d-6920-456b-b1db-6d3395e3be84)

### Example 6 Custom Image
#### template
![object cropped](https://github.com/Rugved-Pandit/mowito/assets/62091349/93368f83-00f9-4f15-bf84-4a6eb66c5d68)
#### test
![image](https://github.com/Rugved-Pandit/mowito/assets/62091349/e7a9d03c-1078-4795-a13a-4875859d2709)
