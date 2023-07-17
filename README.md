**Face Similarity Model using Siamese Network**
This repository contains a face similarity model trained on the LFW (Labeled Faces in the Wild) dataset. The model utilizes a Siamese network architecture, consisting of identical convolutional layers, dense layers, and a distance layer. The goal of the model is to determine whether two input faces belong to the same person or different persons.

**Dataset**
The LFW dataset, which contains 2,200 images, was used for training the face similarity model. The dataset consists of pairs of faces, where same faces are labeled as 0 and different faces are labeled as 1 based on their similarity. The labeling is based on the minimum distance for same faces and maximum distance for different faces. the pair of images are given below:
![download](https://github.com/SinghAnkit1010/Siamese-Network-on-LFW-Dataset/assets/103994994/6eda1f39-90b9-4396-8648-d1b0061d0491)
![download (1)](https://github.com/SinghAnkit1010/Siamese-Network-on-LFW-Dataset/assets/103994994/c93586dc-5196-446e-9d74-56a35f201c85)


**Model Architecture**

The face similarity model employs a Siamese network architecture. It consists of two identical convolutional layers followed by dense layers. On top of these layers, a distance layer is stacked, which computes the distance between the two input faces. The sigmoid activation function is used to project the distances between 0 and 1.


**Loss Function**

Several loss functions were experimented with, including contrastive loss and cross entropy. The binary cross entropy loss function yielded better results for this particular task. It measures the dissimilarity between the predicted similarity and the ground truth labels.

**Model Evaluation**

The performance of the model was evaluated using the recall metric. Since the focus is on minimizing false negatives (different faces predicted as the same), recall was chosen as it provides a measure of false negatives. The model achieved a recall of 65% on the training dataset and 70% on the validation dataset.
