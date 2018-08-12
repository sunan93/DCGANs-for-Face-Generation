# Face Generation using Deep Convolutional Generative Adversarial Networks

In this project, a deep convolutional generative adversarial network has been used to generate faces of celebrities and also for hand-written digit generation. The project is inspired from udacity deep learning nanoDegree program. The following gives the details of the implementation.


### Preprocessing Data:-
The values of the MNIST and CelebA dataset are in the range of -0.5 to 0.5 and are 28x28 dimensional images. MNIST has a single colour channel and CelebA has 3 colour channels. 

### Discriminator Function:-
A three-layer convolutional neural network has been used to implement the discriminator. The first layer contains a filter of size 5x5 with stride=2 and the inputs are padded as well. This filter is applied for 64 layers. So the final output of the first layer transforms the input of size 28x28x(num_channels) to 14x14x64. The same filter and stride is applied on the second layer CNN 128 times giving an output of 7x7x128. The third layer CNN uses the same filter and stride to give an output of 4x4x256. The final output is flattened and is normalized using sigmoid to give the prediction of whether it is a real or a fake image. Batch normalization and leaky relu have been used in each of the intermediate layers.

### Generator Function:-
The generator network is exactly similar to the discrimintor network implemented upside down. The three layer CNN has been implemented in a reverse manner.

### Training:-
The generator tries to generate images which are as close as possible to the real images and the discriminator tries to differentiate between the real and the fake images. The generator and the discriminator are trained alternately to minimize the cross-entropy loss function between the reall and the fake images. 

### Results :-
The outputs for the following parameters have been attached for both the celebA and MNIST dataset.

batch_size = 64
z_dim = 100
learning_rate = 0.0003
beta1 = 0.45

The generator losses for the last few epochs are shown below:-
Epoch 2/2 Step 6110...... Discriminator Loss: 1.1929... Generator Loss: 0.6893
Epoch 2/2 Step 6120...... Discriminator Loss: 1.0025... Generator Loss: 1.1472
Epoch 2/2 Step 6130...... Discriminator Loss: 0.8402... Generator Loss: 1.3703
Epoch 2/2 Step 6140...... Discriminator Loss: 0.6574... Generator Loss: 1.8629
Epoch 2/2 Step 6150...... Discriminator Loss: 0.7212... Generator Loss: 1.5189
Epoch 2/2 Step 6160...... Discriminator Loss: 0.6946... Generator Loss: 2.3419
Epoch 2/2 Step 6170...... Discriminator Loss: 0.7610... Generator Loss: 1.4760
Epoch 2/2 Step 6180...... Discriminator Loss: 1.3046... Generator Loss: 2.6152
Epoch 2/2 Step 6190...... Discriminator Loss: 0.8598... Generator Loss: 1.1478
Epoch 2/2 Step 6200...... Discriminator Loss: 0.7169... Generator Loss: 1.7651

### References 
1. [Udacity Deep Learning Projects](https://github.com/udacity/deep-learning)
2. [Stanford Slides for Generative Adversarial Networks](http://cs231n.stanford.edu/slides/2017/cs231n_2017_lecture13.pdf)
3. [Sunita Sarawagi's Course on Deep Learning](https://www.cse.iitb.ac.in/~sunita/cs726/)
4. [Generative Adversarial Models](https://papers.nips.cc/paper/5423-generative-adversarial-nets.pdf)
