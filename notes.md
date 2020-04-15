## Team Notes

### Meeting discussion

- Get miscImgs.zip
    - In terminal, use command `wget cs.mtsu.edu/~mbo2d/miscImgs.zip`
        - Command should download the zip file containing the first set of images and scores.
    - Important files
        - target.png  # this is the primary target image we will be using.
        - #_model.png # (ex. 0124_model.png) These are the primary model images we will be training on for the networks. 
        - scores/humanScores.txt   # These are the human scores from Galaxy Zoo: Mergers.  Our primary scores we want to recreate.
            - 1st line corresponds to 0000_model.png
            - 2nd line to 0001_model.png
            - etc
        - scores/pCorrScores.txt   # These are the 'perturbedness' scores for the model images. 

- Discuss convolution neural networks.
    - Watch the online lecture.
    - Pay special attention to OLA6.
    
### 

Aric - Paper.  (Abstract done. methodology) CNN example
Jarrett - Milestones, Applying ola6.
Derrick - Demo, ola6 application. ()
Ogden - Comparing two images, regression model, single-layer. 
Shawn - call back funcitons.  displaying weights.  saving weights. 
Devon - CNN, applying ola6


Apr 7
Aric -  ( Created a working CNN, good image shuffle, found noise in human scores ), different size kernel sizes, save weights 
Derrick - ( Looked through demos, found good examples ), Derrick will show demo format, layout, and show us next week. 
Ogden - ( Single layer, example of 2img nn ), two images, expand top data
Jarret - ( Working CNN model )
Shawn - ( CNN difficulties ), pull aric's and create CNN
Devon - ( categorical difficulties ), grab someone else's cnn model and work on it. 

    
### Project code

Needed skills to gain
- Read in images, rescale
- Identify architectures useful for regression, classification, and binary decision models.
- How to structure architecture to read in two images and compare them to one another.


Primary Goal 
1) Visualize weights that have been trained for patterns.
    - Build single layer newtorks that can conveniently visualize weights. 

2) Build code to conveniently train a new regression model on a new system of model images and human scores.
    - Unique to each system. Can be solely based on model images.  Can also compare model image and target image.

3) build general purpose regression model to compare two images.
    - Built across multiple systems. 

Everyone
- Everyone do OLA6, will be great base for working with images.

Misc Projects
1) (Easy) Build networks for identifying perturbedness.
    - This can be done in a couple of different ways.
    - Actual perturbedness values are stored in pCorrScores.txt.  (Ex. .4 is highly perturbed,  .9 is lowly perturbed. )
    1) Model Image
        - Classification model 
            - Choose a perturbedness threshold, ( Ex. p > .85 is bad, p <= .85 is good ), 
            - Use that as training classification
        - Regression Model
            - Try to match the perturbedness value
    2) Use Model and Init Image
        - Have model read both model image and init image and have them compare images to one another. 
        - Create a classification and/or regression model.
    - misc Goals
        - Visualize parts of the galaxies that are crucial to identifying whether image is pertrubed or not.

2) Apply pre-trained convulated weights for images.
    - https://keras.io/applications/
    - Has several pre-trained weights for image classification
        - Identify what kind of classifications they are built for. 
    - Go through weights and visualize the patterns, scan if any patterns are good or bad for our research.


### ToDo list
- (Done) Create Draft proposal
- (Done) Finialize and submit proposal with team.
- (Done) Upload first sample data

### Q's for Dr. Phillips
- How to cite Galaxy Zoo: Mergers data.
- How specific can the milestones be? 
    

## Future notes

Rescale pixel values before sending into NN. 
- Grayscale images traditionally store pixel values as 0-255 int.   
- NN don't like 0 imputs and our images have a lot of black space with 0 pixel values.
- Rescale pixel values to -128->127 or something before sending through NN.

Use pre-trained convoluted weights
- https://keras.io/applications/#available-models
- Several weights are unique to image feature extraction.

Save weights periodically, review test accuracy plot, and use best weights