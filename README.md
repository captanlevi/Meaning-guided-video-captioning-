# Meaning-guided-video-captioning-
This is the code based on our research paper on meaning guided video captioning. The code is written in pytorch.
Here we describe a new approach to train a video captioning neural network , that is not only based on the normal cross entropy loss for the caption but also uses the meaning of the caption.

All the code files should be run in jupyter notebook , the first cell of all the notebooks will provide the information regarding the necessary python modules and required files and their paths , set them according to your comfort.


How use the pretrained model...
 To caption the model use the caption.ipynb file ,run all cells, the caption will be generated after the end cell.
 
 How to train the model....
1) First look at the extract_features file ...
  This is responsible for extracting Object features , VGG16 features and resnet features. Running this file will save all the extracted features at the specified destination.

2) Pretrain the video_model.
  In the main_train.ipynb there are three methods to train the model  train1 , train2 and train3 
  train1 uses regular cross entropy loss.
  train2 uses lets the model generate a caption on its own and then uses metric loss described in the paper.
  train3 again lets the model generate a caption , but uses cross entropy loss.
  
  During pretraining we use train1 only and let the model converge.
  Then use combination of train1 and train3 as described in the paper.
  
3) pretraining the meteric 
   The meteric is a bi directional GRU and its defination is provided in main train itself. Pretraining it would yield better results , the procedure is described in the paper.
   
   
   Link for the Paper https://drive.google.com/file/u/3/d/17GlQGkBcQW-04QDfonAUsZSagwHcstgH/view
