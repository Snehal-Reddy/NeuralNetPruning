# NeuralNetPruning

To view and run this code, click on the ipynb file and you will find an option to view it on Google Colab. Click on it and you can now view and run the code in an easy way.

Apart from StackOverflow, these links were extremely useful during the coding process.
* https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/model_pruning#adding-pruning-ops
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

### Analysis

Red -> Weight pruning

Blue -> Neuron pruning

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Acc.png) 

![alt_text](https://github.com/Snehal-Reddy/NeuralNetPruning/blob/master/images/Loss.png) 


We can observe from the graphs above that we can remove significant parts of network weights without much effect to the model performance. 
For weight pruning, the performance degrades at around 75% removal. Whereas for neuron pruning it is around 50%. Interestingly neuron pruning showed a much more higer drop in performance at around 75% although it started degrading at 50%.
For lower sparsity percentages (< 50%) unit pruning appears to be more computationally efficient, as we always deal with dense matrices. 

### Hypothesis
During weight pruning I realised a significant portion of the weights are near to zero and hence can be pruned with minimal effect to the neural network performance. On the other hand the column norms seem to be a bit more away from zero, beacuse a column will have a mix of small and large weights. Hence there is always higher chance to prune out the heavier weights.

This made me realise the importance of pruning, and that we are able to prune around 50% weights easily without much effect. I think pruning is an overlooked method that is going to get a lot more attention and be used in practice. I am surprised by this result and will use this in my future projects.

### Additional
The task can be done using inbuilt tensorflow libraries and other ways like-
* https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/model_pruning#adding-pruning-ops
* https://www.tensorflow.org/api_docs/python/tf/contrib/model_pruning/Pruning
