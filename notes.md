## Team Notes

### Meeting discussion

- Get data_batch_1
    - while in terminal on jupyter notebook use command 'wget cs.mtsu.edu/~mbo2d/miscImgs.zip'
    - Command should download the zip file containing the first set of images and scores. 

- Everyone build basic code to read images train a train single-layer network.
    - For simplicity, you can turn into classification problem. (1 if > 0.5)

- Discuss convolution neural networks.
    - Watch the online lecture.
    - Pay special attention to OLA6.
    
- New task, someone learn how to apply pre-trained convulated weights for images.

    
- Discuss GIT repository
    - Does everyone know the basics of Git? 
        - Add basic git document
    - Branch structure?
        - Seperate branches for seperate work?   (Good experience with git)
    - You can use terminal and git repository on class juptyer server.

## Immediate To-Do

### Matt
- (Done) Create Draft proposal
- (Working) Finialize and submit proposal with team.
- Ask Dr. Phillips how to cite Galaxy Zoo: Mergers data.
- Upload sample data

### Q's for Dr. Phillips
- How to cite Galaxy Zoo: Mergers data.
- Can we use the JupyterLab server for our project?
    - Would we have a shared workspace?
- How specific can the milestones be? 
    

## Future notes

Rescale pixel values before sending into NN. 
- Grayscale images traditionally store pixel values as 0-255 int.   
- NN don't like 0 imputs and our images have a lot of black space with 0 pixel values.
- Rescale pixel values to -128->127 or something before sending through NN.

Use pre-trained convoluted weights
-https://keras.io/applications/#available-models
- Several weights are unique to image feature extraction.

Save weights periodically, review test accuracy plot, and use best weights