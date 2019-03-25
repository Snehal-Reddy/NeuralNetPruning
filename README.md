# NeuralNetPruning

To view and run this code, click on the ipynb file and you will find an option to view it on Google Colab. Click on it and you can now view and run the code in an easy way.

Apart from StackOverflow, these links were extremely useful during the coding process.
* https://www.tensorflow.org/tutorials/eager/custom_training_walkthrough
* https://danijar.com/structuring-your-tensorflow-models/
* https://gist.github.com/danijar/720394a9071a03413be8a60852374aa4
* https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/model_pruning


### Weight Pruning
I ranked the individual weights in weight matrix and set individual weights of the smallest k% in the weight matrix to zero. This corresponds to deleting connections.
The results are as follows - 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Acc_Wt.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Loss_Wt.png) 


### Neuron Pruning
I ranked the columns of a weight matrix according to their L2-norm and delete the smallest k%, in effect deleting the corresponding output neuron.
The results are as follows-

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Acc_N.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Loss_N.png) 

### Hypothesis

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Acc.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Loss.png) 


We can observe from the graphs above that we can remove significant parts of network weights without much effect to the model performance. 
For weight pruning, the performance degrades at around 75% removal. Whereas for neuron pruning it is around 50%. Interestingly neuron pruning showed a much more higer drop in performance at around 75% although it strted degrading at 50%.
For lower sparsity percentages (< 50%) unit pruning appears to be more computationally efficient, as we always deal with dense matrices. 
This made me relaise the importance of pruning, and that we are able to prune arounf 50% weights easily without much effect. I am surprised this result and will use this in my future projects.
