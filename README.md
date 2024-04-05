# MCQ-Dataset
A dataset containing answers from the answer sheet and examples of student ID filling, used for training machine-readable answer sheet recognition models, divided into answer dataset and ID dataset. For a detailed description of this dataset, **please refer to/data/description.json in this repo.**

## Overview

- Answer dataset: Records examples of answers filled by students, categorized into 'A', 'B', 'C', 'D', 'E' five classes.
- ID dataset: Records examples of student IDs filled, categorized into 0-9 ten classes.

## How To Use

You can use `ImageFolder` in PyTorch to load the dataset in `DataLoader` :

```python
from torchvision import datasets

    train_data = datasets.ImageFolder(root='data/answer_data/train', transform=transform)
    test_data = datasets.ImageFolder(root='data/answer_data/test', transform=transform)

    train_loader = DataLoader(train_data, batch_size=8, shuffle=True)
    test_loader = DataLoader(test_data, batch_size=8, shuffle=False)
```

You can also use `image_dataset_from_directory` in TensorFlow :

```python
import tensorflow as tf

# train
dataset = tf.keras.preprocessing.image_dataset_from_directory(
    directory='data/answer_data/train',  
    batch_size=8, 
    image_size=(256, 256),  
    shuffle=True, 
    seed=123, 
    validation_split=0.2, 
    subset="training",  
)

# validation
validation_dataset = tf.keras.preprocessing.image_dataset_from_directory(
    directory='data/answer_data/test',
    batch_size=8,
    image_size=(256, 256),
    shuffle=True,
    seed=123,
    validation_split=0.2,
    subset="validation",
)

```
## Preview of the images

### Answer Data
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/b6e374fc-174e-4e96-8ef0-1118e0254be3)
![111](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/d7df0d34-ebe7-49d3-8ebe-93e726e56b6f)
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/46b57a23-7648-44a6-ab65-408767bd3538)
![1081](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/993cbf01-d8a5-4280-ac54-1501be0703ab)
![1088](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/a6252b05-5074-4cfb-8e5f-7114c4997ce7)

### ID Data
![67](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/024ec8f1-2278-4bc3-ad3c-68ba938efa8d)
![69](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/435f712d-ad5f-4002-ae4e-b481297c8f4f)
![3](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/7bd32471-c683-4dd2-aa0d-c5aefc3c53d4)
![9](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/9016d359-01bf-460d-a913-2d3a6ced53b0)
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/86a96251-77c9-49e2-bbb8-be8efc96bb99)
![2](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/b367a5ab-0cbc-41a5-845c-ed293cd961dc)
![2](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/49a1648b-3a69-4ca9-ae2a-03c1093ed9a8)
![2](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/e0ee0df2-fdc9-4895-a9dd-ad5112843565)
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/f54fcca9-afb7-4fbd-8fdb-d8fae650d11f)
![50](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/1005f5b9-6d7d-4bc1-be58-a262cfdefb51)



## Terms and Conditions
- This data set comes from the customized answer sheets of the University of Liverpool. If you use other types of answer sheets(such as SAT answer sheets), the recognition results may be inaccurate.
- This dataset does not contain any personal information. All raw data do not come from real exam answer sheets, but are filled in manually by the author(s).
- Commercial use of this dataset is prohibited. If you use this dataset in your project, please include the copyright notice and this permission statement in the software and in all copies of the software.

## Acknowledgements
I would like to thank Mr. Chenwei Yin, Mr. Zekai Gong, Mr. Zijian Wang and Mr. Tianyao Qiu. Together they helped create this dataset. At the same time, I would also like to thank Mr. Gubin Zhao for providing the code for positioning and cropping images.
