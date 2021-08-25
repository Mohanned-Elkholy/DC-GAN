# DC-GAN

# Projection Discrimination
In conditional gans, it is useful to provide information about the class to the discriminator. There are multiple ways to do so, but the most efficient way is to have a dot product of the global sum pooling of the features with an embedding vector. Please note that every embedding vector is unique according to the class. You can read more about projection discrimination in this paper (https://arxiv.org/pdf/1802.05637.pdf)

![image](https://user-images.githubusercontent.com/47930821/130755627-af91d3f2-2d66-4fcf-b656-e87d330d249b.png)
