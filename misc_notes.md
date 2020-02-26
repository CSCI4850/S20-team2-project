## Immediate To-Do

Matt
- (Done) Create Draft proposal
- Ask Dr. Phillips how to cite Galaxy Zoo: Mergers data.
- Upload sample data


## Misc notes
- Rescale pixel values before sending into NN. 
  - Grayscale images traditionally store pixel values as 0-255 int.   
  - NN don't like 0 imputs and our images have a lot of black space with 0 pixel values.
  - Rescale pixel values to -128->127 or something before sending through NN.
