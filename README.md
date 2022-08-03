# Julia_Deep_Neural_Network
Comparing the effect of ordinary neural network and deep neural network

My previous model was like this:
model = Chain(Dense(4,8,σ),Dense(8,2,identity),softmax);
Right now it became:
![image](https://user-images.githubusercontent.com/100655843/182498872-189eaed8-1992-4eab-b095-9e648932d96b.png)

Original:
![image](https://user-images.githubusercontent.com/100655843/182498959-ebb5ac74-1b3d-4639-b6d2-902ddcc7343c.png)
New:
![image](https://user-images.githubusercontent.com/100655843/182498998-6164b4bf-0fc9-4873-a875-98620985b1c6.png)

To test whether more hidden layers can always gain better accuracy, I did a test is adding 15 hidden layers, expecting to get 100% accuracy. However, in my datasets, perhaps the labels is not very large, it return bad accuracy. The reason I guess is that model is over-fitting, and the prediction effect of placing the model on the test data is seriously reduced.

I think when the model with 15 hidden layers to train my real or fake money datasets, the process is like:

1. A neuron receives two inputs of color type and color depth from its previous layer. After weighting, it outputs a new value. The abstract meaning of this value may be interpreted as "color balance";

2. Another neuron also receives the banknote length and banknote width input from its previous layer, and is also weighted to output a new value, the abstract meaning of this value may be interpreted as "regular money";

3. The abstract "color balance" and "regular money" and other features of the previous layer will continue to be input to the next layer and processed in the same way to obtain more higher-level abstract features, such as "Perfection".

4. However, as the hidden layer deepens, the deep abstract features may be too abstract to explain, and the prediction accuracy decreases.



