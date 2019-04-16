vgg random fault injection
This process of random fault injection is:
1. Load model from official released keras model (vgg as an example)
2. Extract all weights and bias in different layer to a vector
3. Set fault ratio
4. Randomly generate weights index and bit index to determine the bit flip in the certain bit position of a single weight
5. After injection, write modified vector back to the network structure

Before using this file, the topology of the network structure is required e.g : total number of weights, total number of layer...
test 