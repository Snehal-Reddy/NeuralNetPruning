# NeuralNetPruning

To view and run this code, click on the ipynb file and you will find an option to view it on Google Colab. Click on it and you can now view and run the code in an easy way.

### Weight Pruning
I ranked the individual weights in weight matrix and set individual weights of the smallest k% in the weight matrix to zero. This corresponds to deleting connections.
The results are as follows - 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/A_P_W.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/L_P_W.png) 


### Weight Pruning
I ranked the columns of a weight matrix according to their L2-norm and delete the smallest k%, in effect deleting the corresponding output neuron.
The results are as follows-

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/A_P_N.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/L_P_N.png) 
