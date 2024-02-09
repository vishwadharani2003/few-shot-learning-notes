# Training siamese network
Siamese networks are a special type of neural network architecture, particularly useful for tasks that involve finding the <span style="color:#15d170">similarity or relationship between two comparable things</span>. They are called "Siamese" because they consist of two identical subnetworks, meaning they have the same architecture and share the same parameters and weights. These networks are effective in applications such as face recognition, signature verification, and few-shot learning tasks.

### Pairwise Similarity Score:

The main goal of a Siamese network in many applications is to compute a pairwise similarity score between two inputs. <mark style="background: #ADCCFFA6;">This score indicates how similar or different the inputs are, according to the task at hand.</mark> For example, in face verification, the score would reflect whether two face images belong to the same person.

### Architecture:

1. **Twin Networks**: The core of the Siamese architecture consists of twin networks that take two separate inputs. These networks are identical, sharing the same parameters, ensuring that the same kind of features are extracted from each input.
    
2. **Feature Extraction**: Each subnetwork in the Siamese architecture acts as a feature extractor. The inputs pass through these networks to produce feature vectors. The architecture of these subnetworks can vary (CNNs for images, RNNs for sequences, etc.) depending on the application.
    
3. **Distance Metric**: The feature vectors produced by the twin networks are then compared using a distance metric or similarity function. Common choices include the Euclidean distance, Cosine similarity, or Manhattan distance. This comparison yields the pairwise similarity score.
    
4. **Loss Function**: Siamese networks are trained using a special loss function, often the contrastive loss or triplet loss. These loss functions are designed to ensure that similar items are brought closer in the feature space, while dissimilar items are pushed apart.
# Siamese network for pairwise similarity score

# Triplet Loss
another method for training the siamese network
- we need to select three images from the entire training set
- 

# Basic idea of few shot learning
- training a Siamese network on large scale training set
- Given a support set of K-way and n-shot
		- K-way means K-classes
		- n-shot means every class has n-sample
		- The training set does not contain the K-classes
- Given a Query ,predict its class
	-use the siamese network to compute similarity  or distance

# Pretraining and fine tuning
- Cosine similarity is used to find how similar two vectors are
- 

	Consider a few-shot segmentation task in medical imaging, where the goal is to segment a particular anatomical structure in MRI scans, but only a few annotated examples are available. A Siamese network can be used as follows:

- **Reference Images**: A small set of MRI scans with annotated segmentation masks for the target structure.
- **Query Image**: An MRI scan without an annotation, for which the segmentation mask needs to be predicted.
- **Process**: The Siamese encoders process the query and each reference image to extract features. Through a comparison mechanism, the network identifies how features from the query image relate to those from the reference images. The decoder uses this information to predict the segmentation mask for the query image, effectively transferring knowledge from the reference images to the query context.

I love avind