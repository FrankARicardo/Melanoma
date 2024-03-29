## Database

Public images of the HAM 10 000 dataset: [link](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T)

10 015 images, 7 skin lesions.

|Lesion             |Images |Dimensions  |Kind of lesion
|-------            |-------  |-------      |-----------
|Melanocytic nevi | 6 705   | 600x450     | Benign |
|Melanoma           | 1 113   | 600x450     | Most dangerous cancer |
|Benign keratosis| 1 099 | 600x450     | Benign 
|Basal cell carcinoma | 514 | 600x450 | Low hazard cancer
|Actinic keratoses | 327 | 600x450 | Low hazard cancer
|vascular lesion | 142 | 600x450 | Benign
|Dermatofibroma | 115 | 600x450 | Benign

## Data augmentation

Data augmentation used to generate images in the classes with less elements

![Alt text](images/data_aug.png?raw=true "Title")

|Lesion             |Images |Dimensions  |Kind of lesion
|-------            |-------  |-------      |-----------
|Melanocytic nevi | 6 705   | 600x450     | Benign |
|Melanoma           | 1 113   | 600x450     | Most dangerous cancer |
|Benign keratosis| 1 099 | 600x450     | Benign 
|Basal cell carcinoma | 514 | 600x450 | Low hazard cancer
|Actinic keratoses | 1635 | 600x450 | Low hazard cancer
|vascular lesion | 710 | 600x450 | Benign
|Dermatofibroma | 575 | 600x450 | Benign

```ruby
# Data augmentation code

imgs ='ISIC_0025612'
labels = 'df'

# OBTAIN SHAPE AND MATRIXS
img = cv2.imread(os.path.join(base_recortadas, imgs) + '.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
ancho = img.shape[1] #columnas
alto = img.shape[0] # filas

# MATRIX TO ROTATE IMAGES
M1 = cv2.getRotationMatrix2D((ancho//2,alto//2),2,1) #2 DEGREES
M2 = cv2.getRotationMatrix2D((ancho//2,alto//2),-2,1) #-2 DEGRES

#######################################
# ORIGINAL
plt.imshow(img)
size = img.shape
plt.axis("off")
plt.title('Original')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
#######################################
# HORIZONTAL
img_lr = tf.image.flip_left_right(img) 

plt.imshow(img_lr)
size = img_lr.shape
plt.axis("off")
plt.title('Left-Right')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
#######################################
# VERTICAL
img_ud = tf.image.flip_up_down(img) 

plt.imshow(img_ud)
size = img_ud.shape
plt.axis("off")
plt.title('Up-Down')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
#######################################
# ROTATION AND BRIGHTNESS
img1 = cv2.warpAffine(img,M1,(ancho,alto))
img_b = tf.image.adjust_brightness(img1, 0.2) 

plt.imshow(img_b)
size = img_b.shape
plt.axis("off")
plt.title('Brillo')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
#######################################
# ROTACION AND CONTRAST
img1 = cv2.warpAffine(img,M2,(ancho,alto))
img_c = tf.image.adjust_contrast(img1, 0.8)
img_c= tf.keras.preprocessing.image.array_to_img(img_c)

plt.imshow(img_c)
#size = img_c.shape
plt.axis("off")
plt.title('Contraste')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
#######################################
# CONTRAST Y BRIGHTNESS
img_bc = tf.image.adjust_contrast(img, 0.8)
img_bc = tf.image.adjust_brightness(img_bc, 0.2)
img_bc= tf.keras.preprocessing.image.array_to_img(img_bc)

plt.imshow(img_bc)
#size = img_bc.shape
plt.axis("off")
plt.title('Contraste y Brillo')
print('Dimensiones:', size[0], 'x' ,size[1])
plt.show()

#######################################
```
## Data centering and resize

The images of the database are rectangular, it is common in Deep Learning to work with square images, that is the reason why we were centered all. In addition, for the work with Vision Transformers the dimension of 224x224 is recommended, so the images were resized.

<figcaption>Original image<figcaption>
<img src="images/o1.JPG" alt="Texto alternativo" width="600" height="450">

<figcaption>Centered image<figcaption>
<img src="images/o2.JPG" alt="Texto alternativo" width="450" height="450">

<figcaption>Resized image<figcaption>
<img src="images/o3.JPG" alt="Texto alternativo" width="224" height="224">
