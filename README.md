
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.

## Program:
``` Python
### Developed By: RICHARDSON A
### Register No: 212222233005 

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("web.jpg", frame)
    print("Image saved as web.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()




## ii) Display the video

videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()  


## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
</br>
<img width="313" alt="Screenshot 2024-09-25 at 8 01 07 PM" src="https://github.com/user-attachments/assets/4bf102c4-0aea-454c-a224-f90eec0c486e">

<img width="1280" alt="Screenshot 2024-09-25 at 4 21 52 PM" src="https://github.com/user-attachments/assets/7c80c31a-b0e9-4277-bcc4-5cd5c2dc28d5">

</br>


### ii) Display the video
</br>
<img width="1280" alt="Screenshot 2024-09-25 at 4 21 52 PM" src="https://github.com/user-attachments/assets/777dd443-1e42-4031-8ab8-d4effa4f7fb6">

</br>


### iii) Display the video by resizing the window
</br>
<img width="1279" alt="Screenshot 2024-09-25 at 4 23 35 PM" src="https://github.com/user-attachments/assets/d4c8de9f-834e-4d28-a9e5-ff4a978523d1">

</br>



### iv) Rotate and display the video
</br>
<img width="1277" alt="Screenshot 2024-09-25 at 7 58 53 PM" src="https://github.com/user-attachments/assets/0b46bf5d-0982-4d1a-b81e-421e787b3495">

</br>


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
