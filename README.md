# Project info
Together with a colleague I'm developing a system that detects the presence of stress based on facial expressions and body language.

Project consists of recording volunteers in a non-stressed environment and stress inducing environment.

We have carefully determined the conditions in which the recordings take place in order not to obscure the results.

Non stressed environment is achieveed by showing the volunteer a video clip of a beautiful scenery combined with relaxing background music.

Stress inducing environment is achieved by showing the volunteer a video clip that consists of series of logical questions (similar to IQ test) along with countdown timer for each problem.


Video recordings are then processed in order to extract the appropriate data and build our dataset. Built dataset will then be used to train a new model which will be able to predict whether or not a person is stressed based on facial expression.

We are also considering adding another module for stress detection besides facial expressions which would be based on body language, in order to improve model's accuracy.

Current state of the project: Collecting video samples and building the dataset

*Notebooks explanations*;

VideoSegmenting - Cuts the sample video into shorter segments according to intervals given in times.txt file.

FacesFromVideo - From each frame in the sample video human face is cropped out and saved. Afterwards, those faces are converted to numpy arrays and saved.

ModifiedFERdataset - FER2013 dataset is modified so that it consists of just two labels, 'expressionless' and 'expressive', 'expressionless' is 'neutral' from the original dataset while 'expressive' includes all the other labels. Images and labels are converted to numpy arrays and saved.

BuildingDataset - Using data from the ModifiedFERdataset a CNN network is trained (achieved val_acc=0.83, val_loss=0.36). After loading faces data constructed in FacesFromVideo we used trained model to predict. Then, images with highest and lowest predictions (most and least expressive) are saved and will be used to build our dataset for stress recognition.
