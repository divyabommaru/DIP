# DIP
## 1.develop a program to display grayscale image using read and write operation 
Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.

Importance of grayscaling –

Dimension reduction: For e.g. In RGB images there are three color channels and has three dimensions while grayscaled images are single dimensional.
Reduces model complexity: Consider training neural article on RGB images of 10x10x3 pixel.The input layer will have 300 input nodes. On the other hand, the same neural network will need only 100 input node for grayscaled images.
For other algorithms to work: There are many algorithms that are customized to work only on grayscaled images e.g. Canny edge detection function pre-implemented in OpenCV library works on Grayscaled images only.
## program:
import cv2 
cv2.imshow('download', img) 
cv2.waitKey(0)
grayimg = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) 
cv2.imshow('Grayscale', grayimg)
cv2.waitKey(0)
cv2.imwrite('download.jpg',grayimg)
cv2.destroyAllWindows()
## imshow()
This function  in pyplot madules of matplotlib lib is used display as an image.
## imwrite()
This method is used to save an image to any storage devices.
## waitKey()
It is a keyboard binding function, the function waits for specified miliseconds for any keyboard event .If you press any key in that time,the program continues.
## destroyAllWindows
simply destroys all the windows we created.
