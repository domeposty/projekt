
Notebooks explanations;

VideoSegmenting - Cuts the sample video into shorter segments according to intervals given in times.txt file.

FacesFromVideo - From each frame in the sample video human face is cropped out and saved. Afterwards, those faces are converted to numpy arrays and saved.

ModifiedFERdataset - FER2013 dataset is modified so that it consists of just two labels, 'expressionless' and 'expressive', 'expressionless' is 'neutral' from the original dataset while 'expressive' includes all the other labels. Images and labels are converted to numpy arrays and saved. 

BuildingDataset - Using data from the ModifiedFERdataset a CNN network is trained (achieved val_acc=0.83, val_loss=0.36). After loading faces data constructed in FacesFromVideo we used trained model to predict. Then, images with highest and lowest predictions (most and least expressive) are saved and will be used to build our dataset for stress recognition.
