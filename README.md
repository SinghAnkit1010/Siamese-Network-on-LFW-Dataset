**Face Similarity Model using Siamese Network:**

This repository contains a face similarity model trained on the LFW (Labeled Faces in the Wild) dataset. The model utilizes a Siamese network architecture, consisting of identical convolutional layers, dense layers, and a distance layer. The goal of the model is to determine whether two input faces belong to the same person or different persons.

**Dataset:**

The LFW dataset, which contains 2,200 images, was used for training the face similarity model. The dataset consists of pairs of faces, where same faces are labeled as 0 and different faces are labeled as 1 based on their similarity. The labeling is based on the minimum distance for same faces and maximum distance for different faces. the pair of images are given below:


![download](https://github.com/SinghAnkit1010/Siamese-Network-on-LFW-Dataset/assets/103994994/6eda1f39-90b9-4396-8648-d1b0061d0491)

![download (1)](https://github.com/SinghAnkit1010/Siamese-Network-on-LFW-Dataset/assets/103994994/c93586dc-5196-446e-9d74-56a35f201c85)


**Model Architecture:**

The face similarity model employs a Siamese network architecture. It consists of two identical convolutional layers followed by dense layers. On top of these layers, a distance layer is stacked, which computes the distance between the two input faces. The sigmoid activation function is used to project the distances between 0 and 1. 

**Model Training:**

During the model training process, we used the RMSProp optimizer, a popular optimization algorithm, to update the neural network weights. The model was trained for 100 epochs.To improve the model's generalization and robustness, we applied data augmentation techniques,like random rotation,random flip etc. to avoid overfitting. Several loss functions were experimented with, including contrastive loss and cross entropy. The binary cross entropy loss function yielded better results for this particular task. It measures the dissimilarity between the predicted similarity and the ground truth labels.

**Model Evaluation:**

During prediction we kept threshhold value of 0.4 that is if distance between two faces are less than 0.4 they belong to same class otherwise from different class.
The performance of the model was evaluated using the recall metric. Since the focus is on minimizing false negatives (different faces predicted as the same), recall was chosen as it provides a measure of false negatives. The model achieved a recall of 60% on the training dataset and 65% on the validation dataset. Furthermore model was evaluated on test data on LFW dataset and we got following results:

|        | precision | recall | f1-score | support |
|--------|-----------|--------|----------|---------|
| Same faces      |   0.71    |  0.33  |    0.45    |    500   |
| Different faces  |   0.56    |  0.86  |    0.68    |    500   |
|--------|-----------|--------|----------|---------|
| accuracy           |           |        |    0.60    |   1000 |
| macro avg      |   0.64    |  0.60  |    0.57    |   1000 |
| weighted avg  |   0.64    |  0.60  |    0.57    |   1000 |

In the context of face similarity, where "Different faces" represents pairs of faces from different individuals, a recall of 0.86 suggests that the model has a relatively high ability to correctly identify different faces, minimizing the occurrence of false negatives.
