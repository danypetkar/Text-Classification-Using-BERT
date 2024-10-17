# Text Classification Using BERT
In this repository, we will use pre-trained deep learning model to process some text. We will then use the output of that model to classify the text. The text is a list of sentences from film reviews. And we will classify each sentence as either speaking "positively" about its subject or "negatively".
## Introduction
This project uses DistilBERT, a distilled version of BERT, for binary sentiment classification of movie reviews. DistilBERT is 60% faster and lighter in size while retaining 97% of BERT's performance. This makes it ideal for real-world applications that require both performance and efficiency.
## Models: Sentence Sentiment Classification
Our goal is to create a model that takes a sentence (just like the ones in our dataset) and produces either 1 (indicating the sentence carries a positive sentiment) or a 0 (indicating the sentence carries a negative sentiment). We can think of it as looking like this:

## Screenshots

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

#### The model is actually made up of two model:
•	DistilBERT processes the sentence and passes along some information it extracted from it on to the next model. DistilBERT is a smaller version of BERT developed and open sourced by the team at HuggingFace. It’s a lighter and faster version of BERT that roughly matches its performance.

•	The next model, a basic Logistic Regression model from scikit learn will take in the result of DistilBERT’s processing, and classify the sentence as either positive or negative (1 or 0, respectively)

The data we pass between the two models is a vector of size 768. We can think of this of vector as an embedding for the sentence that we can use for classification.


![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Dataset
The dataset we will use in this example is SST2, which contains sentences from movie reviews, each labeled as either positive (has the value 1) or negative (has the value 0):

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

#### Preprocessing
•	Tokenization is performed using the DistilBERT tokenizer.

•	Input sentences are padded and truncated to ensure uniform length before feeding into the model.
## Model Architecture
•	DistilBERT Base (Uncased) model is used as the base model.

•	The output of DistilBERT is passed through a fully connected layer to classify the sentiment.

•	A softmax activation function is applied to output probabilities for the two classes (positive or negative).
## Training
#### The training process involves:
    1.	Loading and preprocessing the IMDB dataset.
    2.	Tokenizing the input using the DistilBERT tokenizer.


![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

    3.	Padding
    4.	Masking

Now that we have our model and inputs ready, let's run our model!

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

## Evaluation
After training the model, you can evaluate its performance on the test dataset.
## Conclusion
Using DistilBERT for sentiment classification offers a balance between performance and computational efficiency. While retaining much of BERT's power, DistilBERT is faster and lighter, making it ideal for deployment in environments with limited resources or strict efficiency requirements.


