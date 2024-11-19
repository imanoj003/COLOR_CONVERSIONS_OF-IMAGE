# COLOR_CONVERSIONS_OF-IMAGE
## EXP : 1
## DATE : 12 / 08 / 24
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image

## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.



##### Program and output:
### Developed By:
```
Name : Manoj M
Reg no : 212221240027

```

### i) Read and display the image
```
import cv2 
img = cv2.imread("08.JPG", cv2.IMREAD_COLOR)
cv2.imshow('Image Window', img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>
<br>

![image](https://github.com/user-attachments/assets/2ee76d9b-cebb-4720-92c8-5bc62f451b6d)

### ii) Draw Shapes and Add Text

#### Rectangle
```
import cv2

img = cv2.imread("08.JPG")
start=(0,0)
stop=(500,500)
color=(100,255,100)
thickness=10

res_img=cv2.rectangle(img,start,stop,color,thickness)

cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/e092accd-af75-4193-a6ab-7600f4c73ce5)

#### Circle
```
import cv2

img = cv2.imread("08.JPG")

res=cv2.circle(img,(230,225),150,(255,0,0),10)

cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/bf0c20cf-7c53-4def-b3bd-e0dc00e95f04)

#### Line
```
import cv2

img = cv2.imread("08.JPG")
res = cv2.line(img,(0,0),(500,500),(200,100,205),10)

cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/12a66955-7e3a-4133-835f-1d9882611d16)

#### (4) Add the text "OpenCV Drawing" at the top-left corner of the image.

```
import cv2
image = cv2.imread("img1.png")
image = cv2.resize(image, (400, 300))
text = "OpenCV Drawing"
position = (10, 50)
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255) 
thickness = 2
res = cv2.putText(image, text, position, font, font_scale, color, thickness, cv2.LINE_AA)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/ce398c4f-033d-44e1-892d-541741276853)

### iii) Image color conversion
<br>
<br>

#### BGR and RGB to HSV and GRAY

```
import cv2
img = cv2.imread('img1.png',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/ad512ee5-758e-46d2-975a-66588fb80e87)

#### HSV to RGB and BGR
<br>
<br>

```
import cv2
img = cv2.imread('img1.png')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/8f77628c-915e-4b9f-945c-ee06b8835024)

#### RGB and BGR to YCrCb
<br>
<br>

```
import cv2
img = cv2.imread('img1.png')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/301e5e29-47e1-4dc2-a206-77ce86f43ab2)

#### Split and merge RGB Image
<br>
<br>

```
import cv2
img = cv2.imread('img1.png',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/b37175a9-7ad7-4758-b78b-c08b6b7b248c)

### x) Split and merge HSV Image
<br>
<br>

```
import cv2
img = cv2.imread("img1.png",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/e62af3ef-b281-47cc-bd99-6f3bde16a60e)


### iv) Access and Manipulate Image Pixels

#### (1) Access and print the value of the pixel at coordinates (100, 100)


```
print(f"Pixel value at (100, 100): {pixel_value}")
```
![image](https://github.com/user-attachments/assets/82c7a3a8-025f-41d3-a6b1-f6d7403e8e85)

#### (2) Modify the color of the pixel at (200, 200) to white

```
import cv2
image = cv2.imread('forest.png',1)
image = cv2.resize(image,(400,300))
cv2.imshow('ORIGINAL IMAGE',image)
image[200, 200] = [255, 255, 255] 
cv2.imshow('MODIFIED IMAGE', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/e56f2be2-bd74-425a-a331-22e0c09cc5e3)

### v) Image Resizing

```
cv2.imshow('ORIGINAL IMAGE',image)
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('RESIZED IMAGE', resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/2541aa14-73fe-4b9b-b4b3-b000c133316d)

### vi) Image Cropping

```
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

import cv2
image = cv2.imread('img1.png',1)
image = cv2.resize(image,(400,300))
x, y = 50, 50
width, height = 100, 100
roi = image[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/391c19ba-cfdd-4296-9dce-b894514df26c)


### vii) Image Flipping

#### (1) Flip the original image horizontally and display it.


```
import cv2
image = cv2.imread("img1.png")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/3c27c6f2-188a-49f4-b264-616141d4c277)

#### (2) Flip the original image vertically and display it.

```
import cv2
image = cv2.imread("img1.png")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/cf212cce-e0bf-4a3b-aba8-822063846146)

### viii)Write and Save the Modified Image

```
import cv2
img = cv2.imread("img1.png")
img = cv2.resize(img,(300,200))
cv2.imwrite('boat_pic.jpg',img)
```


![image](https://github.com/user-attachments/assets/91cec2b6-c04f-4d3b-86e1-b4288a209985)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







