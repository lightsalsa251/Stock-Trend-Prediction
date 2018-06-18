# Stock-Trend-Prediction
Predict the stock price trend of Google for the next one month. The data was downloaded from Yahoo Finance. It contains stock prices of google for the last 5 years. Stacked LSTM architecture is used for predictive modelling.
## But what in the world is LSTM?
Long Short Term Memory networks aka LSTMs are a special kind of RNN, capable of learning long term dependencies. They are designed to avoid vanishing and exploding gradient problem that RNN faces for long term dependencies. LSTMs provide a highway for the gradient to propagate backwards.
![Cell](http://colah.github.io/posts/2015-08-Understanding-LSTMs/img/LSTM3-chain.png)
### Each cell has
* c(t) - Cell state vector
* x(t) - Input vector
* Forget Gate Layer - Looks at h(t-1) and x(t) to output what amount of information to throw away
* Input Gate Layer - Decides which value to update
* Cell State Vector - Creates a vector of candidate values
* Output Gate Layer - Decides which parts of the cell state to output
* Output Vector(h(t)) - Some part of cell state in the range of -1 to +1 is the output
## Working
1. The forget gate ouputs values
2. Input gate outputs values that is multiplied by the cell state vector to create an update
3. Multiply previous cell state with the output of forget gate
4. Then we add the result of 2 and 3. This is the new candidate values(C(t)), scaled by how much we decided to update each state value.
5. C(t) is then squashed by tanh layer, multiplied by the output of output gate layer to give h(t)
## Installation
### Download the data and clone this repository
* Clone this repository to your computer.
* Get into the folder using cd Stock-Trend-Predictor.
* Download the data from Yahoo Finance into this directory.
## Installing the requirements
* pip install keras
* pip install tensorflow
* pip install pandas
* pip install matplotlib
## Usage
* Run each cell in the Model_script.ipynb file.
* Save the graph for presentation
## Result
The model is able to predict the trend of stock prices accurately as shown in the graph
