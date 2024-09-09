# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

## Program:
#### Developed By: Manoj M
#### Register Number: 212221240027


## Output:

### i) Read and display the image

```python
     import cv2
    image=cv2.imread('dog.png',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('Arun',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows() 

```

![Screenshot 2024-09-05 183844](https://github.com/user-attachments/assets/6d5a7e42-b921-4b08-a5b1-317beaecbf56)


### ii)Write the image

```python
   image=cv2.imread('dog.png',0)
    cv2.imwrite('demo.png',image)
```

![Screenshot 2024-09-05 190707](https://github.com/user-attachments/assets/52e02cbf-0631-4ad8-8a32-f4fdd2c101a8)


### iii)Shape of the Image

```python
    image=cv2.imread('dog.png',1)
    print(image.shape)
```



### iv)Access rows and columns

```python
import random
    image=cv2.imread('dog.png',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![Screenshot 2024-09-05 185120](https://github.com/user-attachments/assets/6421e9fc-f02e-4914-9637-595cca89167b)


### v)Cut and paste portion of image

```python
    image=cv2.imread('dog.png',1)
    image=cv2.resize(image,(300,300))
    tag =image[150:200,110:160]
    image[110:160,150:200] = tag
    cv2.imshow('image1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![Screenshot 2024-09-05 185257](https://github.com/user-attachments/assets/002060b9-351c-43e6-bd59-0db624ed5863)





### vi) BGR and RGB to HSV and GRAY

```python
    img = cv2.imread('dog.png',1)
    img = cv2.resize(img,(200,200))
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


![Screenshot 2024-09-05 185503](https://github.com/user-attachments/assets/12b96a70-e545-4fc1-a50a-cc35d76ce2dd)



### vii) HSV to RGB and BGR

```python
img = cv2.imread('dog.png')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```


![Screenshot 2024-09-05 185635](https://github.com/user-attachments/assets/d291e5a3-5c0a-40ab-95fe-fca9875ead0a)


### viii) RGB and BGR to YCrCb

```python
img = cv2.imread('dog.png')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-09-05 185741](https://github.com/user-attachments/assets/9c4f98fb-579a-48f6-b4a0-221ba0cedca8)


### ix) Split and merge RGB Image
```python
img = cv2.imread('dog.png',1)
img = cv2.resize(img,(200,200))

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
![Screenshot 2024-09-05 185929](https://github.com/user-attachments/assets/97c1335b-85a0-4254-84ba-e3dafb4444d8)


### x) Split and merge HSV Image
```python
img = cv2.imread("dog.png",1)
img = cv2.resize(img,(200,200))
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
![Screenshot 2024-09-05 190100](https://github.com/user-attachments/assets/84f95481-354f-4393-8d48-9172df78d085)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
