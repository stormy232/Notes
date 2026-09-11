if tensors with diff shapes the smaller tensor will be broadcast to match shape of larger tensor

this can be broken into two steps:
- Axes are add to the smaller tensor to mathc the ndim of larger tensor
- smaller tensor is repeated alongside these new axes to match full shape of larger tensor

dot product aren't symmetric past ndim 1


ReLU  basically whatever input goes into the activation function we take the max of that and 0

so if activation function is f(x) then relu of this is max(0,x) = y-axis value

tensor reshaping:
- reshaping means rearranging rows and columns to match a target shape 

Scaling can be done with a dot product of 2 x 2 matrix with a [horizontal_factor, 0] ,[0, vertical_factor]

Linear transform:
- dot product, scaling and rotations are linear transforms

Affine transforms:
- comb of lin trans and a translation ()

train_images[10:100, :, :] -> this takes a slice of images from 10 to 100 and all 28x28 pixels

generally the first axis in all data tensors will be the samples axis, first axis is called the batch axis or batch dimension

relu and addition are element-wise ops applied independently on each entry in tensor

Dense layer with relu activation:
- affine trans followed by relu

keras.layers.Dense(512, activation="relu")
This layer can be interpreted as a function, which takes as input a matrix and returns
another matrix—a new representation for the input tensor. Specifically, the function
is as follows (where W is a matrix and b is a vector, both attributes of the layer):
output = relu(dot(input, W) + b)