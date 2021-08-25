# DC-GAN

# Projection Discrimination
In conditional gans, it is useful to provide information about the class to the discriminator. There are multiple ways to do so, but the most efficient way is to have a dot product of the global sum pooling of the features with an embedding vector. Please note that every embedding vector is unique according to the class.

You can read more about projection discrimination in this paper (https://arxiv.org/pdf/1802.05637.pdf)

![image](https://user-images.githubusercontent.com/47930821/130755627-af91d3f2-2d66-4fcf-b656-e87d330d249b.png)

---

# Spectral-Norm penalization
In the discriminator, the spectral norm penalization is applied. Usually in deep learning, it is harmful to let the model lean on a small subset of weights. Therefore weight regularization is sometimes essential. However directly penalizing the weights may restrict the learning process. Thus, instead of penalizing weights, the highest eigen value of the weights is penalized instead. Thus, it prevents the space of the weight matrix to be oriented in one specific direction.

Pros: it helps stabilize the training, since the over-trained discriminator makes the generator diverge during the training

Cons: it makes the training slower

You can learn more about the spectral norm discriminators here (https://arxiv.org/pdf/1802.05957.pdf)


---

# Conditional Batch Norm
The original batch norm forces the distribution to be uniform with two parameters, gamma and beta. In CBN (conditional batch norm), both gamma and beta are drawn from an embedding space that is unique to every class. Therefore, conditioning the class helps choose the right parameters that will help later in image formation. 

You can read more about CBNs here (https://arxiv.org/pdf/1707.00683v3.pdf)

---
# Self attention
Self attention is basically a combination of three convolutional layers. Two of them creates an attention map by having them multiplied together. Later the attention map passes through a softmax to both determine the most important features and normalize the map. This is critical in helping the generator develop an idea of the whole convolutional map and determine the most effective features to generate

You can learn more about self attention here (https://arxiv.org/pdf/1805.08318.pdf)

![image](https://user-images.githubusercontent.com/47930821/130756911-2c41c37b-e2d8-4b27-91dc-c8c22655bb3d.png)
