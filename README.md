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
## Scalar transformation:Image resizing refers to the scaling of images. Scaling comes handy in many image processing as well as machine learning applications. It helps in reducing the number of pixels from an image .
## cv2.resize() method refers to the scaling of images. Scaling comes handy in many image processing as well as machine learning applications. It helps in reducing the number of pixels from an image .
## imshow() function in pyplot module of matplotlib library is used to display data as an image
## program:
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
## Rotation:
## Image rotation is a common image processing routine used to rotate images at any desired angle. This helps in image reversal, flipping, and obtaining an intended view of the image. Image rotation has applications in matching, alignment, and other image-based algorithms. OpenCV is a well-known library used for image processing.
## program:
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


## 3.Develope a program to convert a colour image grayscale and binary image
## Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.
A binary image is a monochromatic image that consists of pixels that can have one of exactly two colors, usually black and white.
## cv2.threshold works as, if pixel value is greater than a threshold value, it is assigned one value (may be white), else it is assigned another value (may be black). 
## program:
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

## 4.Develop a program to convert a colour image to different colour space
Color spaces are a way to represent the color channels present in the image that gives the image that particular hue
## BGR color space: OpenCV’s default color space is RGB. 
## HSV color space: It stores color information in a cylindrical representation of RGB color points. It attempts to depict the colors as perceived by the human eye. Hue value varies from 0-179, Saturation value varies from 0-255 and Value value varies from 0-255. 
## LAB color space :
L – Represents Lightness.A – Color component ranging from Green to Magenta.B – Color component ranging from Blue to Yellow.
The HSL color space, also called HLS or HSI, stands for:Hue : the color type Ranges from 0 to 360° in most applications 
## Saturation : variation of the color depending on the lightness.
## Lightness :(also Luminance or Luminosity or Intensity). Ranges from 0 to 100% (from black to white).
## YUV:Y refers to the luminance or intensity, and U/V channels represent color information. This works well in many applications because the human visual system perceives intensity information very differently from color information.
## cv2.cvtColor() method is used to convert an image from one color space to another. 
## program:
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
## output:

![image](https://user-images.githubusercontent.com/72590819/104435718-b5594c00-55b2-11eb-946c-83228eb6651a.png)
![image](https://user-images.githubusercontent.com/72590819/104435858-e2a5fa00-55b2-11eb-9d8c-a3f7c59583a9.png)
## 5.develop a program to create an image from 2D array. Generate array of random size.
2D array can be defined as an array of arrays. The 2D array is organized as matrices which can be represented as the collection of rows and columns. However, 2D arrays are created to implement a relational database look alike data structure.
## numpy.zeros() function returns a new array of given shape and type, with zeros.
## Image.fromarray(array) is creating image object of above array
## program:

import numpy as np
from PIL import Image
import cv2 as C
array = np.zeros([100,200,3],dtype=np.uint8)
array[:,:100]=[150,128,0]
array[:,100:]=[0,0,255]
img=Image.fromarray(array)
img.save('download.jpg')
img.show()
C.waitKey(0)
## output:
![image](https://user-images.githubusercontent.com/72590819/104436059-2567d200-55b3-11eb-94cd-b44f2a86c40e.png)


## 6. Develop a program to find sum and mean of a set of images.Create n number of images and read the directory and perform operation.
You can add two images with the OpenCV function, cv. add(), or simply by the numpy operation res = img1 + img2.
The function mean calculates the mean value M of array elements, independently for each channel, and return it:" This mean it should return you a scalar for each layer of you image
## The append() method in python adds a single item to the existing list.
## listdir() method in python is used to get the list of all files and directories in the specified directory.
## program:

import cv2
import os
path = 'C:\Pictures'
imgs = []

files = os.listdir(path)
for file in files:
    filepath=path+"\\"+file
    imgs.append(cv2.imread(filepath))
i=0
im = []
for im in imgs:
    #cv2.imshow(files[i],imgs[i])
    im+=imgs[i]
    i=i+1
cv2.imshow("sum of four pictures",im)
meanImg = im/len(files)
cv2.imshow("mean of four pictures",meanImg)
cv2.waitKey(0)
## output:
![image](https://user-images.githubusercontent.com/72590819/104436384-8b545980-55b3-11eb-920c-8539526f3a98.png)
## 7.Write a program to find the sum of neighbour values in a matrix.
## program:
import numpy as np

M = [[1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]]

M = np.asarray(M)
N = np.zeros(M.shape)
def sumNeighbors(M,x,y):
    l = []
    for i in range(max(0,x-1),x+2): # max(0,x-1), such that no negative values in range()
        for j in range(max(0,y-1),y+2):
            try:
                t = M[i][j]
                l.append(t)
            except IndexError: # if entry doesn't exist
                pass
    return sum(l)-M[x][y] # exclude the entry itself
for i in range(M.shape[0]):
    for j in range(M.shape[1]):
        N[i][j] = sumNeighbors(M, i, j)

print ("Original matrix:\n", M)
print ("Summed neighbors matrix:\n", N)
## output:
![image](https://user-images.githubusercontent.com/72590819/104441777-23554180-55ba-11eb-89b3-300fc7997850.png)
## 8.Write a C++ program to perform operator overloading.

In C++, we can make operators to work for user defined classes. This means C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading.
## program
#include <iostream>
using namespace std;
class matrix
{
 int r1, c1, i, j, a1;
 int a[10][10];

public:int get()
 {
  cout << "Enter the row and column size for the  matrix\n";
  cin >> r1;
  cin >> c1;
   cout << "Enter the elements of the matrix\n";
  for (i = 0; i < r1; i++)
  {
   for (j = 0; j < c1; j++)
   {
    cin>>a[i][j];

   }
  }
 
 
 };
 void operator+(matrix a1)
 {
 int c[i][j];
  
   for (i = 0; i < r1; i++)
   {
    for (j = 0; j < c1; j++)
    {
     c[i][j] = a[i][j] + a1.a[i][j];
    }
   
  }
  cout<<"addition is\n";
  for(i=0;i<r1;i++)
  {
   cout<<" ";
   for (j = 0; j < c1; j++)
   {
    cout<<c[i][j]<<"\t";
   }
   cout<<"\n";
  }

 };

  void operator-(matrix a2)
 {
 int c[i][j];
  
   for (i = 0; i < r1; i++)
   {
    for (j = 0; j < c1; j++)
    {
     c[i][j] = a[i][j] - a2.a[i][j];
    }
   
  }
  cout<<"subtraction is\n";
  for(i=0;i<r1;i++)
  {
   cout<<" ";
   for (j = 0; j < c1; j++)
   {
    cout<<c[i][j]<<"\t";
   }
   cout<<"\n";
  }
 };

 void operator*(matrix a3)
 {
  int c[i][j];

  for (i = 0; i < r1; i++)
  {
   for (j = 0; j < c1; j++)
   {
    c[i][j] =0;
    for (int k = 0; k < r1; k++)
    {
     c[i][j] += a[i][k] * (a3.a[k][j]);
    }
  }
  }
  cout << "multiplication is\n";
  for (i = 0; i < r1; i++)
  {
   cout << " ";
   for (j = 0; j < c1; j++)
   {
    cout << c[i][j] << "\t";
   }
   cout << "\n";
  }
 };

};

int main()
{
 matrix p,q;
 p.get();
 q.get();
 p + q;
 p - q;
 p * q;
return 0;
}
## output:
![image](https://user-images.githubusercontent.com/72590819/105163064-43a86300-5ac8-11eb-89ae-a8a732059692.png)
## 9.Develop a program to find the neighbours of each element in the matrix.
## program:
import numpy as np
ini_array = np.array([[1, 2,5, 3], [4,5, 4, 7], [9, 6, 1,0]])
print("initial_array : ", str(ini_array));
def neighbors(radius, rowNumber, columnNumber):
    return[[ini_array[i][j]if i >= 0 and i < len(ini_array) and j >= 0 and j < len(ini_array[0]) else 0
            for j in range(columnNumber-1-radius, columnNumber+radius)]
           for i in range(rowNumber-1-radius, rowNumber+radius)]
neighbors(1,2,1)
## output:
![image](https://user-images.githubusercontent.com/72590819/105341529-13c69180-5b94-11eb-8a2a-b5f5e9fe4863.png)
## 10.write a program to display the nagation of an image 
The negative of an image is achieved by replacing the intensity ‘i’ in the original image by ‘i-1’, i.e. the darkest pixels will become the brightest and the brightest pixels will become the darkest. Image negative is produced by subtracting each pixel from the maximum intensity value.
## Program:
import cv2
import numpy as np
img=cv2.imread("flower.jpg")
cv2.imshow("original",img)
cv2.waitKey(0)	
img_neg=255-img;
cv2.imshow("negation",img_neg)
cv2.waitKey(0)
##output:
![image](https://user-images.githubusercontent.com/72590819/107623930-f2931700-6c0e-11eb-992f-71a1068ed90a.png)
![image](https://user-images.githubusercontent.com/72590819/107623969-0179c980-6c0f-11eb-8ca8-314bf8b28cf6.png)


## 11.write a program on thresholding
Thresholding is the simplest method of segmenting images
Types of thresholding
cv2.THRESH_BINARY
cv2.THRESH_BINARY_INV
cv2.THRESH_TRUNC
cv2.THRESH_TOZERO
cv2.THRESH_TOZERO_INV
## program:
import cv2  
import numpy as np  
image1 = cv2.imread('images.jpg')  
img = cv2.cvtColor(image1, cv2.COLOR_BGR2GRAY)
ret, thresh1 = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(img, 120, 255, cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO_INV)
cv2.imshow('Binary Threshold', thresh1)
cv2.imshow('Binary Threshold Inverted', thresh2)
cv2.imshow('Truncated Threshold', thresh3)
cv2.imshow('Set to 0', thresh4)
cv2.imshow('Set to 0 Inverted', thresh5)  
if cv2.waitKey(0) & 0xff == 27:  
    cv2.destroyAllWindows()
## output:
![image](https://user-images.githubusercontent.com/72590819/107618086-d63eac80-6c05-11eb-9339-ea0b6da1b13d.png)
![image](https://user-images.githubusercontent.com/72590819/107618134-e9ea1300-6c05-11eb-8824-2c895498a22f.png)
![image](https://user-images.githubusercontent.com/72590819/107618162-fa01f280-6c05-11eb-9f0c-d2de30a1c35b.png)
![image](https://user-images.githubusercontent.com/72590819/107618185-02f2c400-6c06-11eb-828a-105a58c8d9a5.png)
![image](https://user-images.githubusercontent.com/72590819/107618220-0e45ef80-6c06-11eb-9056-9710e239a07d.png)
## 12.program to perform gamma transformation 
Power-law (gamma) transformations can be mathematically expressed as s = cr^{\gamma}. Gamma correction is important for displaying images on a screen correctly, to prevent bleaching or darkening of images when viewed from different types of monitors with different display settings.
cv2.hconcat() it is used as cv2.hconcat() to concatenate image horizontally.here h means horizontal. 
## program :
import cv2
import numpy as np
img = cv2.imread("flower.jpg")
gamma_two_point_two=np.array(255*(img/255)**2.2, dtype='uint8')
gamma_point_four=np.array(255*(img/255)**0.24,dtype='uint8')
img3 = cv2.hconcat([gamma_two_point_two,gamma_point_four])
cv2.imshow('a2',img3)
cv2.waitKey(0)
cv2.destroyAllWindows()



