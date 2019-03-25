# NeuralNetPruning

To view and run this code, click on the ipynb file and you will find an option to view it on Google Colab. Click on it and you can now view and run the code in an easy way.

Apart from StackOverflow, these links were extremely useful during the coding process.
* https://www.tensorflow.org/tutorials/eager/custom_training_walkthrough
* https://danijar.com/structuring-your-tensorflow-models/
* https://gist.github.com/danijar/720394a9071a03413be8a60852374aa4


### Weight Pruning
I ranked the individual weights in weight matrix and set individual weights of the smallest k% in the weight matrix to zero. This corresponds to deleting connections.
The results are as follows - 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/A_P_W.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/L_P_W.png) 


### Neuron Pruning
I ranked the columns of a weight matrix according to their L2-norm and delete the smallest k%, in effect deleting the corresponding output neuron.
The results are as follows-

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/A_P_N.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/L_P_N.png) 

### Hypothesis
We can observe from the graphs above that we can remove significant parts of network weights without much effect to the model performance. 
