# Anomaly-Detection-Using-Autoencoders

Anomaly Detection means identifying outliners in the given data.There are different algorithms to identify outliners in the data but the one we are going to use today is Autoencoder. Autoencoders is a Artificial Neural Network model used in Deep Learning. Autoencoders consist of an encoder and decoder type of architecture. The encoder compresses the data into latent space and decoder tries to rebuild the data from latent space.This encoder and decoder type of architecture of Autoencoder is helpful in determining outliners in the data.

## How does Autencoder work in determing anomalies in the data

First of all the outliners are separated from the normal data.Therefore two separate datasets are created one with outliners and one with normal data.Then the Autoencoders are trained on the dataset with normal data.This results in encoder and decoder learning only to build normal data and not any outliners.Once the model is trained a threshold value is calculated between the normal data and the reconstructed data.This threshold value is calculated by root mean square error(RMS) or by mean absolute error(MAE).Now lets assume a case when a outliner is given as input to the autoencoder model. Since model has only learned to rebuild normal data it will fail to rebuild the outliner data.Then we will calculate RMS or MAE for outliner data and compare it to the threshold value, it will obviously be higher.Hence we can flag that outliner as anomaly.

https://user-images.githubusercontent.com/56148821/143690827-72e563cb-939a-4412-9cf1-cba7c4696680.png

## Implementation

I have used this technique in this repository to identify plant leaves having disease or not.Diseased leaves are classified as anomalies and hence are outliners to the dataset. The file "Neural Networks.ipynb" contains the code for Autoencoder and Classfication model for the leaves.For testing purposes a website was designed with neural network as backend and deployed on the local network.

### Frontend of the website
https://user-images.githubusercontent.com/56148821/143690655-d9f546cb-2aed-4d9d-8924-3dd17d8c0d8e.png

### Plant leave that is Healthy
https://user-images.githubusercontent.com/56148821/143690668-47070035-0250-4ead-880e-7ab54e8dbfd9.png

### Plant leave that is Diseased(Anomaly)
https://user-images.githubusercontent.com/56148821/143690672-88ef6f6f-2a8a-4ab4-91af-b8906ebb2fd7.png

## Files
Neural Network.ipynb : It contains the code for Autoencoder model and Classification model
Template and Static directories: These contain the html files and static images for the frontend
app.py : Is the backend of the website
auto-plant_final.h5 and class-plant3_final : These are the H5 files of the models developed 
**Dataset can be found here:** https://drive.google.com/file/d/1fRbpW7be7Wgs-OLfq-ggASbIL8DNuBvE/view?usp=sharing
The dataset is in compressed numpy array format.The code to read the file can be found in "Neural Networks.ipynb".

