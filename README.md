# MCQ-Dataset
A dataset containing answers from the answer sheet and examples of student ID filling, used for training machine-readable answer sheet recognition models, divided into answer dataset and ID dataset. For a detailed description of this dataset, please refer to/data/description.json in this repo.


## Terms and Conditions
- This data set comes from the customized answer sheets of the University of Liverpool. If you use other types of answer sheets(such as SAT answer sheets), the recognition results may be inaccurate.
- This dataset does not contain any personal information. All raw data do not come from real exam answer sheets, but are filled in manually by the author(s).
- Commercial use of this dataset is prohibited. If you use this dataset in your project, please include the copyright notice and this permission statement in the software and in all copies of the software.


## How to use

You can use `ImageFolder` in PyTorch to load the dataset in `DataLoader` :

```python
from torchvision import datasets

    train_data = datasets.ImageFolder(root='data/answer_data/train', transform=transform)
    test_data = datasets.ImageFolder(root='data/answer_data/test', transform=transform)

    train_loader = DataLoader(train_data, batch_size=64, shuffle=True)
    test_loader = DataLoader(test_data, batch_size=64, shuffle=False)
```

## Preview of the images
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/b6e374fc-174e-4e96-8ef0-1118e0254be3)
![111](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/d7df0d34-ebe7-49d3-8ebe-93e726e56b6f)
![1](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/46b57a23-7648-44a6-ab65-408767bd3538)
![1081](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/993cbf01-d8a5-4280-ac54-1501be0703ab)
![1088](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/a6252b05-5074-4cfb-8e5f-7114c4997ce7)


answer data
![67](https://github.com/NomotoK/MCQ-Dataset/assets/99944622/024ec8f1-2278-4bc3-ad3c-68ba938efa8d)
id data


