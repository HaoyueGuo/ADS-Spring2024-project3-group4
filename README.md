# Project: ClimSim - Machine Learning for Climate Modeling


### [Full Project Description](doc/project3_desc.md)

<img src="https://leap-stc.github.io/ClimSim/_images/fig_1.png" alt="climsim" width="300"/>

Term: Fall 2023

+ Team 4
+ Team members
	+ team member Chen Yanzhao
	+ team member Guo Haoyue
	+ team member Jiang Tianyi
	+ team member Zhou Yawen
	+ team member 5

+ Project summary: For the Model 1, we use the first 10k images with clean labels as test data and the remaining 40k images with noisy labels as training data. Then we do validation by looking  at the label and test data after the image test passes the model. Our model 1 use 3 3 CNN layers; The 1st and 2nd Conv2D layers with 32 filters and a kernel size​ of 3x3. The third Conv2D layer with 64 filters and a kernel size of 3x3.​Despite its simplicity, this model achieved a notable accuracy of 47.73%, significantly improving upon the baseline model, although at the cost of increased training time. which is around 413.44 second.

 
Then we hope to further improve accuracy through model2. we We divided model2 into three steps.
The first step (building a clean label prediction model): Use the first 10,000 pictures and their noisy labels as input, and the clean label as the output for training. The specific method is: convert the noisy label into the form of one-hot encoding, and use the first 10,000 pictures. After convolution kernel pooling, dropout and other operations, a vector is finally generated. This vector is concatenated with the dirty label in the form of one-hot encoding, and then connected to a fully connected layer to train the model on the first 10,000 pictures. with testing.
 
The second step (get the clean labels of 50,000 data), apply this model to the next 40,000 pictures, generate their possible clean labels, put these 40,000 clean labels together with the first 10,000 clean labels, so We got 50,000 pictures with clean labels.
 
The third step (build a more accurate image classification model), build a new CNN model on these 50,000 images, use these 50,000 images as input, and use its clean label as output for training. This model is what we finally use for image classification.
 
	

**Contribution statement**: ([default](doc/a_note_on_contributions.md)) All team members contributed equally in all stages of this project. All team members approve our work presented in this GitHub repository including this contributions statement. 

Following [suggestions](http://nicercode.github.io/blog/2013-04-05-projects/) by [RICH FITZJOHN](http://nicercode.github.io/about/#Team) (@richfitz). This folder is orgarnized as follows.

```
proj/
├── lib/
├── data/
├── doc/
├── figs/
└── output/
```

Please see each subfolder for a README file.
