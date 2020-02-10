# A-Deep-Learning-Framework-for-Assessing-Physical-Rehabilitation-Exercises

The codes in this repository are based on the eponymous research project <a href="https://arxiv.org/abs/1901.10435">A Deep Learning Framework for Assessing Physical Rehabilitation Exercises</a>. The proposed framework for automated quality assessment of physical rehabilitation exercises encompasses metrics for quantifying movement performance, scoring functions for mapping the performance metrics into numerical scores of movement quality, techniques for dimensionality reduction, and deep neural network models for regressing quality scores of input movements via supervised learning. 

# Data
<a href="https://www.webpages.uidaho.edu/ui-prmd/">UI-PRMD dataset</a> of rehabilitation movements is used. It contains full-body skeletal joint displacements for 10 movements performed by 10 healthy subjects. The codes employ 117-dimensional skeletal angles acquired with a Vicon optical tracker for the deep squat exercise. The subset of movement data used in the paper can be downloaded fom the "Reduced Data Set" section on the website.

# Neural Network Codes
The codes were developed using the Keras library.
* SpatioTemporalNN_Vicon - the proposed deep spatio-temporal model in the paper.
* CNN_Vicon - a basic convolutional neural network for predicting movement quality scores.
* RNN_Vicon - a basic recurrent neural network for predicting movement quality scores.
* Autoencoder_Dims_Reduction - a model for reducing the dimensionality of Vicon-captured movement data.
* SpatioTemporalNN_Kinect - implementation of the proposed deep learning model for predicting quality scores on Kinect-captured data.

# Distance Functions
The codes were developed using MATLAB.
* Maximum Variance - distance functions on reduced-dimensionality data using the maximum variance approach.
* PCA - distance functions on reduced-dimensionality data using PCA.
* Autoencoder - distance functions on reduced-dimensionality data using an autoencoder neural network.
* No Dimensionality Reduction - distance functions on full-body skeletal data (117 dimensions).

Please see the List of Files and Functions document for a complete list and brief descriptions of all files in the repository. 

# Use
* Run "Prepare_Data_for_NN" to read the movements data, and perform pre-processing steps, such as length alignment and centering. Alternatively, skip this step, since the outputs are saved in the Data folder (Data_Correct.csv and Data_Incorrect.csv).
* Run "Autoencoder_Dims_Reduction" to reduce the dimensionality of the movement data. Alternatively, skip this step, since the outputs are saved in the Data folder (Autoencoder_Output_Correct.csv and Autoencoder_Output_Incorrect.csv).
* Run "Prepared_Labels_for_NN" to generate quality scores for the individual movement repetitions. Alternatively, skip this step, since the outputs are saved in the Data folder (Labels_Correct.csv and Labels_Incorrect.csv)
* Run "SpatioTemporalNN_Vicon" to train the model and predict movement quality scores on the Vicon-captured movement data.
* Run "SpatioTemporalNN_Kinect" to train the model and predict movement quality scores on the Vicon-captured movement data.

A slighly different version of the codes with verified reproducibility is also published on Code Ocean and can be accessed via the following link: <a href="https://codeocean.com/capsule/7213982/tree/v3">https://codeocean.com/capsule/7213982/tree/v3</a>

# License
MIT License

# Acknowledgments
This work was supported by the <a href="https://imci.uidaho.edu/get-involved/about-cmci/">Institute for Modeling Collaboration and Innovation (IMCI)</a> at the University of Idaho through NIH Award #P20GM104420.
