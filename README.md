# SOLO

SOLO (Segmenting Objects by Locations) is a state-of-the-art instance segmentation algorithm that was introduced in 2019 by the researchers at the Chinese University of Hong Kong. It is a fully convolutional neural network that operates directly on the pixel level, without requiring object proposals or anchor boxes.

The key innovation of SOLO is its use of a novel segmentation head that predicts object instances by assigning a unique mask to each pixel in the image. Unlike other instance segmentation algorithms, which rely on two-stage approaches that first detect objects and then perform segmentation, SOLO performs both tasks simultaneously.

SOLO divides an input image into a grid of cells and predicts object instances for each cell. It does this by predicting a set of learnable masks, one for each object instance, and a set of objectness scores that indicate the probability of an object being present in each cell.

During training, SOLO uses a hybrid loss function that combines a binary cross-entropy loss for objectness scores and a mask loss that measures the similarity between predicted and ground-truth masks. This loss function encourages the network to learn to predict accurate masks for each object instance while also correctly identifying the presence or absence of objects in each cell.



## Dataloader
We have written a custom class called “MyDataset” which creates our train and test set. The train set and test set are then sent to the dataloader function to create the train and test dataloaders respectively.
## Solo Class
We have implemented the CNN and the generate target functions inside the Model CNN Class. We have also included the loss and forward functions and finally the functions to perform training and validation on the network. We have also performed the post processing and visualization of masks in this code cell.

## Issues faced 
We ran our model for 40 epochs on the entire dataset using the Google Colab GPU, but we were not able to complete training. The memory available was not enough to train our entire model, so we had to use Colab Pro with the Premium GPU. Initially, in the first few training runs, the Mask loss in our model was constant, there was no decrease. There was a bug in our dataloader which we fixed and finally we were able to get the mask loss to decrease with epochs. We also had to slightly tweak the threshold values in our code to get better mask outputs for our images. Overall, our model was generating good masks at the correct locations. The performance and accuracy of our model could be improved further with additional compute resources and time. Due to overlapping assignments and Mid Terms, we were not able to train our model well enough to be absolutely robust.

# Results

<p align="center">
  <img src="/Images/bird_pyr2_overlay.png"  hspace="20"/>
  <img src="/Images/bird_pyr2.png"/>
</p>
<p align="center">
  <img src="/Images/human_pyr2_overlay.png" hspace="20"/>
  <img src="/Images/human_pyr2.png"/>
</p>
<img src=Images/output_cat.png> <p></p>
<p align="center">
  <img src="/Images/output_human.png" hspace="20"/>
  <img src="/Images/output_vehicle.png"/>
</p>


# To Run

- Download the dataset from

[Images](https://drive.google.com/file/d/1Xyo9voEtL8fFf0gh7NY8L0cC6z8mZDrl/view?usp=share_link)
[Masks](https://drive.google.com/file/d/1GPiIFdKIuKZ03tpC5vWluD8RZMAbI7Tv/view?usp=share_link)
[Labels](https://drive.google.com/file/d/18Ug7UI55wzIrflL-PuovJoRP2-FTxMzV/view?usp=share_link)
[Bboxes](https://drive.google.com/file/d/1e3il3wqT4rfUeVLAYFP_Q1hV7_8VgDtM/view?usp=share_link)

- Change the path in the Python Notebook
- Run Cells Accordingly
