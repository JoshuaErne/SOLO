# SOLO

## Dataloader
We have written a custom class called “MyDataset” which creates our train and test set. The train set and test set are then sent to the dataloader function to create the train and test dataloaders respectively.
## Solo Class
We have implemented the CNN and the generate target functions inside the Model CNN Class. We have also included the loss and forward functions and finally the functions to perform training and validation on the network. We have also performed the post processing and visualization of masks in this code cell.

##Issues faced 
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
<img src=Images/allboundingboxes.png> <p></p>
<img src=Images/postlowconfsupression.png> <p></p>

# Observation
