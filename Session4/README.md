# Objective:

99.4% validation accuracy

Less than 20k Parameters

Less than 20 Epochs

No fully connected layer


# Approach

1.Three convolution layers

2.Used batchnorm and Drop out(0.15) at the first two convolutional layers

3.Final convolution layer with 10 channels 

4.Used GAP (Global Average Pooling) at the third convolutional layer to bring down the image size from 3 X 3 to 1 X 1


# Network parameters

Total number of parameters: 18990


# Hyper parameters

Learning rate - 0.01

Batch size - 128

Drop out - 0.15


# Results

Reached an accuracy of 99.43% first at 9th epoch, 99.56% at 12th epoch and is consistent.
