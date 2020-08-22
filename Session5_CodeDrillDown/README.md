# Session 5 Assignment

## Model 1

**Target:**
Build a base model with 
* <15k Parameters and <15 Epochs

**Results:**
Number of convolutional layers: 3
Parameters: 13934
Epochs = 15
Train Accuracy: 98.56%
Test Accuracy: 98.60%

**Analysis:**
* Without dropout and batch norm - Our model isn't reaching the expected >99.4% accuracy
* Having brought down the channel size in the convolutional layers has reduced the number of parameters from 20k to 13k.


## Model 2

**Target:**
Build a base model with 
* <10k Parameters and achieve >99.3% test accuracy with <15 Epochs

**Results:**
Number of convolutional Blocks: 2
Parameters: 9646
Epochs = 1
Train Accuracy: 99.66%
Test Accuracy: 99.38%

**Analysis:**
* Included BatchNorm - Learning is faster and able to attain accuracy close to 99.4% (~99.33%) after the few initial layers.
* Large amounts of overfitting observed
* Having brought down the channel size in the convolutional layers has reduced the number of parameters from 13k to 9k.

## Model 3

**Target:**
Address the overfitting issue in the model

**Results:**
Parameters: 9646
Epochs = 15
Train Accuracy: 99.30%
Test Accuracy: 99.43%

**Analysis:**
* Included Image augemtation to reduce overfitting.
* Test Accuracy is consistently above 99.4% in last few epochs

## Model 4
**Target:**
Add LR scheduler to improve the model's learning capability and push the test accuracy further
Add small dropout to encourage more training of the model

**Results:**
Parameters: 9646
Epochs = 15
Train Accuracy: 99.14%
Test Accuracy: 99.55%

**Analysis:**
* Adding the LR scheduler to reduce the LR rate in the model 0.1x after 6 epochs
* Test Accuracy is consistently above 99.4% in last few epochs
