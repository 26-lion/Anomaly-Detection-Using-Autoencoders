# Anomaly-Detection-Using-Autoencoders

Anomaly Detection means identifying outliners in the given data.There are different algorithms to identify outliners in the data but the one we are going to use today is Autoencoder. Autoencoders is a Artificial Neural Network model used in Deep Learning. Autoencoders consist of an encoder and decoder type of architecture. The encoder compresses the data into latent space and decoder tries to rebuild the data from latent space.This encoder and decoder type of architecture of Autoencoder is helpful in determining outliners in the data.

## How does Autencoder work in determing anomalies in the data

First of all the outliners are separated from the normal data.Therefore two separate datasets are created one with outliners and one with normal data.Then the Autoencoders are trained on the dataset with normal data.This results in encoder and decoder learning only to build normal data and not any outliners.Once the model is trained a threshold value is calculated between the normal data and the reconstructed data.This threshold value is calculated by root mean square error(RMS) or by mean absolute error(MAE).Now lets assume a case when a outliner is given as input to the autoencoder model. Since model has only learned to rebuild normal data it will fail to rebuild the outliner data.Then we will calculate RMS or MAE for outliner data and compare it to the threshold value, it will obviously be higher.Hence we can flag that outliner as anomaly.

## Implementation

I have used this technique in this repository to identify plant leaves having disease or not.Diseased leaves are classifies as anomalies and hence are outliners to the dataset. The file "Neural Networks.ipynb" contains the code for Autoencoder and Classfication model.
