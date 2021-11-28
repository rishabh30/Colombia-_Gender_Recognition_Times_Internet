

# Project Title

## Colombia - Gender Recognition Challenge (Times Internet) (Aug 2019)



## Problem Statement
Build a solution to identify their gender by understanding how they interact with digital contents.

## Project structure
├── data\
│   ├── sample_submission.csv\
│   ├── test.csv\
│   └── train.csv\
├── main.ipynb\
├── Gender_Recognition.pptx\
├── requirements.txt\
└── License

### Prerequisites

- GPU(s) with 16Gb RAM (e.g. Tesla V100)

```bash
pip install -r requirements.txt
```

### Usage

### Data Description 
Dataset length - 36179293. 
Sample data of 1st row (Url followed by other features, followed by Gender ) :- 
- timesofindia.indiatimes.com city navi-mumbai msedcl-plans-strategy-for-ghansoli-power-faults articleshow 68444737.cms,F
### Approach
- Assuming Url will contain the most relevant description of the data in squeezed form which contains title, description and other most relevant parameters in the encoded form separated by ‘/’  and also due to computational limitations I extracted URL inputs to train the model.
- I combined  the dataset - Url on the basis of dataset - UserId i.e. instead of having multiple Url with same UserId now one UserId will possess multiple Url separated by space.
- For seperation I converted the data into the numpy array to reduce the time complexity of the model.
- I built own tokenized vocabulary of combined training and test dataset using CountVectorizer.
- I set the number of maximum features to be 7000(vocab-size) which consists of words with frequency greater than 100 and limit maximum frequency to 30 percent of the size of dataset as above this will contain less information.

#### Summary
 
- CountVectorizer
- sparse_categorical_crossentropy loss
- Adam Optimizer
- Keras
- Fully Connected Neural Network
- L2 Regularizer