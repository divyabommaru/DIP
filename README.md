# DIP
## 1.develop a program to display grayscale image using read and write operation 
Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.

Importance of grayscaling –

Dimension reduction: For e.g. In RGB images there are three color channels and has three dimensions while grayscaled images are single dimensional.
Reduces model complexity: Consider training neural article on RGB images of 10x10x3 pixel.The input layer will have 300 input nodes. On the other hand, the same neural network will need only 100 input node for grayscaled images.
For other algorithms to work: There are many algorithms that are customized to work only on grayscaled images e.g. Canny edge detection function pre-implemented in OpenCV library works on Grayscaled images only.
## program:
import cv2 
image=cv2.imread('picture.jpg',0) 
cv2.imshow('grayscale',image)
cv2.waitKey(0)
cv2.imwrite('gray scale',image)
cv2.destroyAllWindows()
## imshow()
This function  in pyplot madules of matplotlib lib is used display as an image.
## imwrite()
This method is used to save an image to any storage devices.
## waitKey()
It is a keyboard binding function, the function waits for specified miliseconds for any keyboard event .If you press any key in that time,the program continues.
## destroyAllWindows
simply destroys all the windows we created.
## output:
![image](https://user-images.githubusercontent.com/72590819/104425163-568dd580-55a6-11eb-8757-8898f0fa0f82.png)


## 2.develop a program to perform linear transformation of an image[scaling and rotation]?
Scalar transformation:
import cv2 
import numpy as np
src=cv2.imread('download.jpg',cv2.IMREAD_UNCHANGED)
scale_p=200
width=int(src.shape[1]*scale_p/100)
height=int(src.shape[0]*scale_p/100)
dsize=(width,height)
result=cv2.resize(src,dsize)
cv2.imwrite('downloa.jpg',result)
cv2.imshow('original',result)

cv2.waitKey(0)
## output:

![image](https://user-images.githubusercontent.com/72590819/104428858-f8afbc80-55aa-11eb-95b4-e98b74f399ad.png)
import cv2 
import numpy as np
src=cv2.imread('download.jpg')
image=cv2.imshow('download.jpg',src) 
windowsname=image
image=cv2.rotate(src,cv2.ROTATE_90_CLOCKWISE)

cv2.imshow('windowsname',image)

cv2.waitKey(0)

## output:
![image](https://user-images.githubusercontent.com/72590819/104429962-2b0de980-55ac-11eb-9032-2a85c4128229.png)


## 4.Develope a program to convert a colour image grayscale and binary image
import cv2
originalImage=cv2.imread('download1.jpg')
grayImage = cv2.cvtColor(originalImage,cv2.COLOR_BGR2GRAY)
(thresh, blackAndWhiteImage) = cv2.threshold(grayImage,127,225,cv2.THRESH_BINARY)
cv2.imshow('Black White Image', blackAndWhiteImage)
cv2.imshow('OriginalImage', originalImage)
cv2.imshow('Gray Image', grayImage)
cv2.waitKey(0)
cv2.destroyAllWindows()
## output:
![image](https://user-images.githubusercontent.com/72590819/104435096-fe5cd080-55b1-11eb-8be5-3fd4ad79a850.png)
![image](https://user-images.githubusercontent.com/72590819/104435390-585d9600-55b2-11eb-84d7-ed5dadb69c74.png)

5.Develop a program to convert a colour image to different colour space

import cv2 
img = cv2.imread('download1.jpg') 
img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV) 
cv2.imshow('hsv', img) 
cv2.waitKey(0)
img = cv2.cvtColor(img, cv2.COLOR_BGR2LAB) 
cv2.imshow('lab', img) 
cv2.waitKey(0)
img = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb) 
cv2.imshow('crcy', img) 
cv2.waitKey(0)
img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) 
cv2.imshow('gray', img) 
cv2.waitKey(0)
cv2.destroyAllWindows()
##output:

![image](https://user-images.githubusercontent.com/72590819/104435718-b5594c00-55b2-11eb-946c-83228eb6651a.png)
![image](https://user-images.githubusercontent.com/72590819/104435858-e2a5fa00-55b2-11eb-9d8c-a3f7c59583a9.png)






