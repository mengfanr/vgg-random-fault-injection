vgg random fault injection:

Platform:
Keras

Instruction:
This program is used to inject bit-flip fault in different selected weights. The weights are chosen randomly following certain pre-determined fault ratio and the bit-flip position in each seleted weight is also determined randomly. This program uses VGG19 as an example and it can be used to inject faults in other network models which can be loaded into Keras.
Before using this program, the topology of the network structure is required e.g : total number of weights, total number of layer .etc. These information can be obtained in Keras after loading corresponding network model.

Process description:
The input of this program is the pre-trained model offered in Keras and the output is a model with injected faults. The weights and bias in the loaded network will be extracted and put into a large vector. According to the fault ratio, the program will randomly determine the total number of weights to be changed. After the fault injection, the faulty vector will be write 
back to the model with the same data type and strucutre.

Usage:
Q: How to change fault ratio?
A: There is a parameter called fault_ratio to determine the fault ratio in each iteration.
Q: How many models can I get?
A: The number of models can be determined by the number of iterations you set in the for loop. In addition, the program will delete/save the model at last. The model you generate in the loop will suffer accumulate fault. For example, if the loop have 5 iteration and fault ratio is 5%, the first model will have 5% fault and the second model will have extra 5% fault based 
on the first one. If you want to generate many model with the same fault ratio, you can change the postion of deleting/saving model.
Q: Can this progroam selectively insert errors?
A: Yes. As long as you create an array in advance and chang the inject postion in the loop. Next version will support load exact position from a file and record the position of fault to a file.