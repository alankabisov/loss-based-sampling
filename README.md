# Loss Based Sampling 

In this work I will try to implement and test Loss Based Sampling (LBS) and compare it with 'vanilla' training on whole dataset. The idea behind LBS is following:
- We train on whole dataset
- At first iteration we make forward pass on whole dataset -> compute loss -> take 80% of samples with the highest loss and use them for backward pass
- On second iteration we take those 80% of samples and do forward pass and again compute loss -> take 80% of samples with the highest loss and use them for backward pass and so on
- On every 5th iteration we start from the begining and train on whole dataset and repeat steps as described above.

For testing purposes I will use [MNIST](http://yann.lecun.com/exdb/mnist/) dataset and [LeNet5](http://yann.lecun.com/exdb/publis/pdf/lecun-01a.pdf) architecture which was initially adapted for this dataset.