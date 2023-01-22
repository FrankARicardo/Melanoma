# Automated Melanoma Detection using Deep Learning

Project presented to obtain the Master Degree

## KeyWords

Deep Learning. Image classification. Transfer learning. Convolutions. Vision Transformers

## Database

Public images of the HAM 10 000 dataset: (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T)

10 015 images, 7 skin lesions.

|Lesion             |Images |Dimensions  |Kind of lesion
|-------            |-------  |-------      |-----------
|Nevus melanocítico | 6 705   | 600x450     | Lesión benigna |
|Melanoma           | 1 113   | 600x450     | Lesión maligna con mayor mortalidad |
|Queratosis seborreica| 1 099 | 600x450     | Lesión benigna 
|Carcinoma basal | 514 | 600x450 | Lesión maligna de bajo riesgo
|Queratosis actínica | 327 | 600x450 | Lesión maligna de bajo riesgo
|Lesión vascular | 142 | 600x450 | Lesión benigna
|Dermatofibroma | 115 | 600x450 | Lesión benigna

## Data augmentation

Data augmentation used to generate images in the classes with less elements

![Alt text](relative/path/to/img.jpg?raw=true "Title")
