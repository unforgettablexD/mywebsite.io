---
layout: project_post
title:  "Ancient Language Handwritten Recognition Under Data Deficient Condition"
summary: "Improving handwritten character recognition for ancient Indian languages using Capsule Networks under limited data conditions."
author: arnav
date: '02024-01-27'
category: ['AI', 'Capsule Networks', 'Handwritten Recognition']
tags: ['AI', 'Capsule Networks', 'Handwritten Character Recognition', 'Sanskrit', 'Tamil', 'EMNIST']
thumbnail: https://www.dropbox.com/s/s46msiyhqzwwy8c/sys_block_1_crop.png?dl=0&raw=1
keywords: AI, capsule networks, handwritten character recognition, ancient languages, Sanskrit, Tamil
usemathjax: false
permalink: /project/ancient-language-handwritten-recognition/
---

# Ancient Language Handwritten Recognition Under Data Deficient Condition

This project focuses on improving handwritten character recognition for ancient Indian languages using Capsule Networks, particularly under conditions of limited data.

## Introduction

The project addresses the challenge of recognizing handwritten characters in ancient Indian languages, which often lack substantial labeled training data. By leveraging Capsule Networks and innovative data augmentation techniques, the goal is to improve recognition accuracy with very small datasets.

## Methodology

The system comprises several key steps:

1. Initial training of the CapsNet model
   ![sys_block_1](https://www.dropbox.com/s/s46msiyhqzwwy8c/sys_block_1_crop.png?dl=0&raw=1)

2. Generating instantiation parameters and reconstructed images
   ![sys_block_2](https://www.dropbox.com/s/4jj1ffshh0ogjh3/sys_block_2_crop.png?dl=0&raw=1)

3. Applying decoder re-training techniques
   ![sys_block_3](https://www.dropbox.com/s/0aiheph4ov68sh9/sys_block_3_crop.png?dl=0&raw=1)

4. New image data generation
   ![sys_block_4](https://www.dropbox.com/s/dt5ma39m60z9tr2/sys_block_4_crop.png?dl=0&raw=1)

5. Training the CapsNet model afresh with the new dataset
   ![sys_block_5](https://www.dropbox.com/s/bn8djgwnhiunyz1/sys_block_5_crop.png?dl=0&raw=1)

## Usage

Clone this repository:
```bash
git clone https://github.com/unforgettablexD/Ancient-Language-Handwritten-Recognition-Under-Data-Deficient-Condition.git
```

### Execution of Pickle File (hdf5, h5)

We have provided hdf5, h5 files to show the model's accuracy. To run the pickle file and get the accuracy mentioned in the results, follow these steps:

1. Install Anaconda.
2. Create an environment and clone the repository:
   ```bash
   conda create --name pickleenv python=3.11.5
   conda activate pickleenv 
   pip install -r require_pickle.txt
   ```

3. To get the accuracy for Sanskrit, run:
   ```bash
   python sanskrit_run_pickle.py
   ```

4. To get the accuracy for Tamil, run:
   ```bash
   python tamil_run_pickle.py 
   ```

5. For EMNIST, run:
   ```bash
   python emnist_run_pickle.py
   ```

### Execution of Code

All the datasets are already added to the code base. However, if you want to check them, here are the links:
- [Tamil dataset](https://www.kaggle.com/datasets/sudalairajkumar/tamil-nlp)
- [Sanskrit dataset](https://www.kaggle.com/datasets/ashokpant/devanagari-character-dataset/data)
- [EMNIST dataset](https://www.nist.gov/itl/products-and-services/emnist-dataset)

To set up the environment:
```bash
conda create --name myenv python=3.6.8
conda activate myenv 
pip install -r requirements.txt
```

To train the model:
```bash
python main.py --cnt 190
```
Here `190` is the number of training samples per class.

To generate new images:
```bash
python main.py -dg --save_dir emnist_bal_200/ -w emnist_bal_200/trained_model.h5 --samples_to_generate 10
```

To train the fresh CapsNet model:
```bash
python textcaps_emnist_bal.py --cnt 200
```

To generate new images:
```bash
python textcaps_emnist_bal.py -dg --save_dir emnist_bal_200/ -w emnist_bal_200/trained_model.h5 --samples_to_generate 10
```

## Results

Despite using only 190 training samples per class, our model achieved comparable accuracy to state-of-the-art models:

| Dataset       | State-of-the-Art Model Accuracy (Full training set) | Our Model (190 Samples/Class) |
|---------------|-----------------------------------------------------|------------------------------|
| Sanskrit      | 98.47% (Acharya et al., 2015)                       | 95.27%                       |
| EMNIST-Digits | 99.79% (Dufoorq & Bassett, 2017)                    | 99.64%                       |
| Tamil         | 98.04% (Ulaganathan et al., 2020)                   | 95.86%                       |

Our approach demonstrates that it's feasible to train accurate models for ancient language character recognition with limited datasets.

## Contact

For inquiries and further information, please contact [kumararn@usc.edu].
```
