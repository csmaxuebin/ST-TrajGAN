﻿# This code is the source code implementation for the paper "ST-TrajGAN：A Synthetic Trajectory Generation Algorithm for Privacy Preservation"！
# Abstract
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/8.png)
The rapid development of location-based services(LBS) exposes large-scale trajectory data to the risk of privacy leakage. In order to enhance the trajectory privacy protection while improving the trajectory utility, this paper proposes an efficient and secure deep learning model ST-TrajGAN (Semantic and Transformer-based Trajectory Generative Adversarial Networks) for trajectory data generation and publication. First, a semantic trajectory encoding model is introduced to preprocess the trajectory points. Second, a synthetic trajectory with more uncertainty and practicality is generated by learning the spatial-temporal and semantic features of real trajectory data. In addition, a new TrajLoss loss metric function is designed to measure the trajectory similarity loss of the trained deep learning model. Finally, the effectiveness of the generated synthetic trajectories and the utility of the model is evaluated by TUL and TSP values on the real LBS datasets.
# Experimental Environment

```
- Python 3.6 (Anaconda Python recommended)
- nltk
- pandas
- scipy
- tqdm
- scikit-learn
- tensorboard
- tensorflow==1.13.1(for tensorboard visualizations)
- tensorflow-gpu==1.13.1
- numpy==1.18.5
- Keras==2.2.4
- geohash2==1.1
- Intel Core i5 CPU 2.3GHz and 8GB RAM 
```

## Datasets

```
- Foursquare NYC, Geolife, Gowalla datasets
```

## Experimental Setup

### Hyperparameters

 -  epochs = 5000
 - learning rate = 0.001
 - batch size = 256
 ### Evaluation Metrics：
- **Privacy Evaluation:**
1.**Trajectory-User Linking (TUL)：** A smaller TUL value indicates a higher level of difficulty in linking users, signifying enhanced - privacy for trajectories
- Utility Evaluation
-Hausdorff distance（HDD）：The Hausdorff distance serves as a metric for quantifying the distance between two sets and is commonly utilized to assess the spatial dissimilarity between two trajectories.
-Trajectory sharing percentage（TSP）：The Trajectory Sharing Percentage is a metric that measures the similarity between synthetic and corresponding real trajectories by averaging the similarity scores across all pairs. A higher TSP signifies a closer match between the synthetic and actual trajectory data, indicating the effectiveness of the synthetic data in mirroring real-world patterns.
-Frequency distribution of visits
## Python Files
 -   **train.py**:  This file is used to train and run an LSTM based TrajGAN model.
-   **losses.py**: This code defines the loss functions of the generator and discriminator for training and optimizing GAN models.
-   **predict.py**:This code is used to generate and save synthetic trajectory data.
-   **TUL_test.py**: This code loads training and testing data, constructs and compiles a classifier model, and uses the model to predict and evaluate the test data.
## Experimental Results
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/1.png)Table II presents the Trajectory-User Linking (TUL) values for three different models across the three datasets. A smaller TUL value indicates a higher level of difficulty in linking users, signifying enhanced privacy for trajectories.
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/3.png)
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/2.png)The Hausdorff distances, as outlined in Table III, represent the mean values calculated across multiple iterations for each dataset, as depicted in Figure 5. The visualization in Fig. 5 illustrates the Hausdorff distances, revealing a decreasing trend for each model as the number of training iterations increases across the three datasets. 
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/4.png)
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/5.png)The TSP figures listed in Table III reflect the mean similarity scores calculated for all trajectories within the dataset. Fig.6 shows the TSP of TUL values for Acc@5 as well as for different datasets. where (a) and (b) are for the NYC dataset, (c) and (d) are for the Geolife dataset, and (e) and (f) are for the Gowalla dataset. 
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/6.png)Figures 7 shows s the temporal and categorical visit frequency distributions
![输入图片说明](https://github.com/csmaxuebin/ST-TrajGAN/blob/main/picture/7.png)Table IV  assesses the influence of varying learning rates, loss metric functions, and different levels of random noise on the performance metrics in the Trajectory-User Linking (TUL) task. 

## Updata log

```
- {24.06.15} Uplode overall framwork code and readme file
```
