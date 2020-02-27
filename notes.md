## Team Notes

### Meeting discussion

- Give introduction to COMS research at MTSU and the Galaxy Zoo: Mergers data.

- Read and discuss proposal 
    - Ask for additional ideas to add to proposal
    - Mention that we could do other cool related stuff not directly related to the research.
    
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
    

## Misc notes

Rescale pixel values before sending into NN. 
- Grayscale images traditionally store pixel values as 0-255 int.   
- NN don't like 0 imputs and our images have a lot of black space with 0 pixel values.
- Rescale pixel values to -128->127 or something before sending through NN.