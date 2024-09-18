# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) Draw Shapes and Add Text.

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
1.  Draw a line from the top-left to the bottom-right of the image.

2.	Draw a circle at the center of the image.

3.	Draw a rectangle around a specific region of interest in the image.

4.	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
1.	Convert the image from RGB to HSV and display it.
2.	Convert the image from RGB to GRAY and display it.
3.	Convert the image from RGB to YCrCb and display it.
4.	Convert the HSV image back to RGB and display it.

### Step4:
1.	Access and print the value of the pixel at coordinates (100, 100).
2.	Modify the color of the pixel at (200, 200) to white.

### Step5:
Resize the original image to half its size and display it.
### Step6:
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
1.	Flip the original image horizontally and display it.
2.	Flip the original image vertically and display it.

### Step8:
Save the final modified image to your local directory.


## Program:
### Developed By:Manoj M
### Register Number: 212221240027


## Output:

### 1. Read and display the image
i.Load an image from your local directory and display it.
```
import cv2
image=cv2.imread('dog.png',1)
image = cv2.resize(image, (400, 300))
cv2.imshow('NATUREK',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 182842](https://github.com/user-attachments/assets/82005b08-d9f6-4f65-961c-735778dd774c)


### Draw Shapes and Add Text
(1) Draw a line from the top-left to the bottom-right of the image.
```
import cv2
image = cv2.imread("dog.png")
image = cv2.resize(image, (400, 300))
res = cv2.line(image, (0, 0), (image.shape[1], image.shape[0]), (255,0,0), 10)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183001](https://github.com/user-attachments/assets/8c568849-737e-4f67-a011-8d9c4ed6f9d6)


2. Draw a circle at the center of the image.
```
import cv2
image = cv2.imread("dog.png")
image = cv2.resize(image, (400, 300))
height, width, _ = image.shape
center_coordinates = (width // 2, height // 2)
res = cv2.circle(image, center_coordinates, 120, (0, 255, 0), 10)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183035](https://github.com/user-attachments/assets/ee8e13ed-1239-4b89-90cf-f741dc31984b)


3.Draw a rectangle around a specific region of interest in the image.
```
import cv2
image = cv2.imread("dog.png")
image = cv2.resize(image, (400, 300))
start = (150, 100)
stop = (300, 200)
color = (255, 255, 100)
thickness = 10           
res_img = cv2.rectangle(image, start, stop, color, thickness)
cv2.imshow('WINDOW', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183055](https://github.com/user-attachments/assets/e0371050-fe9a-4d19-8a14-e8b21b104431)



4.Add the text "OpenCV Drawing" at the top-left corner of the image.
```
import cv2
image = cv2.imread("dog.png")
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


![Screenshot 2024-09-12 183109](https://github.com/user-attachments/assets/5682bcd1-0061-48e2-a48c-ff6d78485963)

### iii)Image Color Conversion
(i)Convert the image from RGB to HSV and display it
```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
hsv = cv2.cvtColor(image,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183131](https://github.com/user-attachments/assets/0e6e28f8-3030-41d4-87cf-3adaef5bb3c7)


(2) Convert the image from RGB to GRAY and display it.

```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
gray = cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


![Screenshot 2024-09-12 183159](https://github.com/user-attachments/assets/40cbf2cb-2068-4596-8e3e-3f5ac3db5bd8)


(3) Convert the image from RGB to YCrCb and display it.
```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
YCrCb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183221](https://github.com/user-attachments/assets/8c3a68d3-1aac-4853-b871-909fe8103be1)



(4) Convert the HSV image back to RGB and display it.
```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(300,200))
cv2.imshow('ORIGINAL IMAGE',image)
RGB = cv2.cvtColor(image,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',RGB)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183240](https://github.com/user-attachments/assets/05b76b1c-6f2f-42f4-a62a-8436935ef8c7)



### iv)Access and Manipulate Image Pixels
(1) Access and print the value of the pixel at coordinates (100, 100)
```
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")
```
![Screenshot 2024-09-12 183250](https://github.com/user-attachments/assets/d9db2939-3721-492a-89aa-19547fc495b7)




(2) Modify the color of the pixel at (200, 200) to white
```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(400,300))
cv2.imshow('ORIGINAL IMAGE',image)
image[200, 200] = [255, 255, 255] 
cv2.imshow('MODIFIED IMAGE', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183309](https://github.com/user-attachments/assets/06067f1d-e855-4b64-b9c7-17a2bf82c1f3)



### v)Image Resizing:
Resize the original image to half its size and display it.
```
cv2.imshow('ORIGINAL IMAGE',image)
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('RESIZED IMAGE', resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183321](https://github.com/user-attachments/assets/516b1545-9f7c-4d88-9c36-24bef584cced)



### vi)Image Cropping
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```
import cv2
image = cv2.imread('dog.png',1)
image = cv2.resize(image,(400,300))
x, y = 50, 50
width, height = 100, 100
roi = image[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183336](https://github.com/user-attachments/assets/a60fb1e9-58d6-412c-bb8d-2dd7d8862388)


### vii)Image Flipping:
(1) Flip the original image horizontally and display it.
```
import cv2
image = cv2.imread("dog.png")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-09-12 183351](https://github.com/user-attachments/assets/e4c7919d-f99b-43ed-ad97-ff92b225fed3)



(2) Flip the original image vertically and display it.
```
import cv2
image = cv2.imread("dog.png")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


![Screenshot 2024-09-12 183406](https://github.com/user-attachments/assets/5a3ebad5-d54c-4475-a582-3299318e102b)


### viii)Write and Save the Modified Image
Save the final modified image to your local directory.
```
import cv2
img = cv2.imread("dog.png")
img = cv2.resize(img,(300,200))
cv2.imwrite('nature_pic.jpg',img)
```

![Screenshot 2024-09-12 183419](https://github.com/user-attachments/assets/87a46cd3-dd0b-4c63-9600-d9f7901b1c6d)


## Result:

Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.






