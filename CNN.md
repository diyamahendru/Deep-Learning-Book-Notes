# Convolutional Neural Networks

CNNs or Convolutional Neural Networks are a kind of neural network that perform extremely good to a grid like topology like an Image, time-series data(1D Grid).
The name implies that the neural network uses the convolution operation.
I will here try explain the working of CNNs in a brief manner 
Convolutional neural networks are used because they leverage three important ideas that help machine learning algorithms. 1.Sparse Interactions
2.Parameter Sharing
3.Equivariant Representations
4.Working with imputs of different sizes

## Sparse Interactions
In traditional Neural Networks matrix multiplication is used which means that every output unit necessarily interacts with the input units. However Convolutional Neural Netrorks have Sparse Interactions or Sparse connectivity/Weights. This is acomplished by making the size of the kernal smaller than the size of the input image.
For example we may want to detect an image of a dog which may contain thousands of pixels while the kernal has a much less cardinality compared to the input image matrix
Thus we need o store lesser parameters which imporove the memory reuirments and statistical efficiency and computing the output requires fewer operations. ELABORATE THIS
for example if there is an input image of size
mXn then the matrix multiplication will require mXn parameters leading to a runtime of O(mXn). if we use a kernal of size kXn then the runtime would be O(kXn).
It is possible for many applications to keep the size k magnitudes smaller than the value M.
Parameter Sharing/ Tied weights
This refers to using of the same parameter for more than one time(kernals). In a traditional Neural network the weight is exactly used once when using the output of the layer. It is multiplied by one element of the input and is never used. In a CNN the kernel is used at every position of the input according to the design of the network(Padding, Strides, etc). This suggests that rather than learning different parameters for a seperate location, we can learn only a set of values. This does not affect the runtime of the network but it does reduce the storage requirments of the network.
As the size (kXm) is much smaller than the size of the image thus convolution is much faster(efficient) than the standard matrix multiplication in terms of memory requirments.
Equivariant Representations TODO
### The Pooling operation
A typical CNN layer consists of three stages:
## Input -> Convolution -> Non Linearity -> Pooling -> Next stage
Genrally the combination of consecutive Convolution, linearity and pooling refers to a single layer of a neural network.
Pooling replaces a bunch of matrix elements with a statistical summary of them. Max pooling may take the maximum value from a bunch of value of pixels.
In all cases though the motive is to make the representation invariant to the small changes/translations to the input.
Invarience to translation means that if we translate the input by small amount most of the pooled outputs remain unchanged. This property comes useful weather we want to determine whether there is a face in an image rather than pin pointing it’s exact pixel location.
Because pooling summerizes the response of a neighbourhood of values of matrix it is possibe to have fewer amount of pooling units than the detector units which reduces the parameters of the next layer and thus increasing the computational efficiency and reduced memory requirments,
This operation is important for many applications such as when variable sized inputs are given to the network pooling can be used to alter the size of the input.

## Structured Outputs
CNNs can be used to output a high dimension data structured object rater than just to predict a class label for the input. Typically this object is a tensor S. Where Si, j, k is an individual element, where i, k are pixels belonging to the class i.

