# Classification Of Time Series Using RNN
This project is part of the exam of Artificial Neural Networks and Deep Learning course at Politecnico
di Milano, and it corresponds to the second challenge. The aim of the project is to classify samples in
the multivariate time series format. In other words, since this is a classification problem, the objective
is to correctly map the information contained in the features calculated over time to their labels.


The project will describe the data exploration and preprocessing steps in order to prepare and understand
the data, and the implementation of the classification using several approaches: RNN, LSTM, Bidirectional LSTM, 1DConv, Feedforward Neural Networks, GRU, LSTM-
1DConv.

It is possible to check all the details of the project from the pdf in this repository, together with the notebooks of the models.

## Data
The dataset consists of 2429 time series, each having one of the 12 possible labels (integer form 0 to
11). Each time series is composed of 36 time-steps, each having 6 features.

## Preprocessing
The splitting of the initial dataset has been performed obtaining 4
sets: a training set with 80% of the total data, the correspondent set of targets, a validation set with
20% of the total data and the correspondent set of targets. The test set was not created and splitted
because the model will be tested on a hidden and private test set.

Initially, no normalization has been used, keeping the time sequences with the original values. After
some experiements, the data has been scaled using different approaches: Standard scaling, MinMax scaling, Robust scaling.

In short, after the very first experiment where the normalization has been performed before split-
ting, the normalization has been performed after the splitting: the scalers has been applied to the
training data, and then the validation and the hidden test sets has been scaled with the parameters of
the training data. This ensures that the model is evaluated on truly unseen data, and the evaluation
metrics provide an accurate measure of the model’s performance on new, unseen data.

In order to solve the unbalance of the classes, two approaches have been used: Class weights, and Oversampling and undersampling.

For performing data augmentation, oversampling techniques introduced before may
be seen as augmentation techniques. Moreover,
data augmentation has also been performed by creating duplicates of the data with some noise inside
generated form a Gaussian distribution.

## Models
The models proposed are: RNN, LSTM, Bidirectional LSTM, 1DConv, Feedforward Neural Networks, GRU, LSTM-
1DConv.

## Results
Overall, the 1DConv model achieved the best results in terms of validation accuracy, followed by
BidirLSTM, LSTM+1DConv, and GRU. This suggests that convolutional neural networks and bidi-
rectional processing can be effective for capturing temporal patterns in time series data, and that combining different types of neural networks can be useful for improving classification accuracy.

## Conclusions
These results taught us that our models, even if theoretically very different from each
other, couldn’t overcome the 75% accuracy with the inputs we were using. That’s another reason
why we tried to manipulate input data to extract “more information” from them, using for example
oversampling, interpolation and bagging.

## Group Components

| Cognome | Nome | e-mail | Codice Persona |
| --- | --- | --- | --- |
| La Greca  | Michele Carlo | michelecarlo.lagreca@mail.polimi.it | 10864460 |
| Giuffrida |  Andrea | andrea.giuffrida@mail.polimi.it | 10643540 |
| Nicolis |  Nicholas | nicholas.nicolis@mail.polimi.it | 10867841 |

