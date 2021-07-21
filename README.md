# Text-Generation

# Report
## Summary of model-
I have done the text generation task by two ways character-wise text generation and word-wise text generation.
## Character-Wise Text Generation
I build a text generator model by building Recurrent Long Short Term Memory Network by character wise training the network which takes sequences of characters up to sequence of length 150 as an input and it generated the next character of that sequence.
From dataset in the form of .csv file which contains URL of the article. I created .txt file of some articles of covid-19 from different URL’s. For training the model target sequences I made which are shifted one position right form the input sequences along with the new character that is predicted to follow the sequence.
In text generator model I used embeddings of dimensions 256 which maps input character to 256-dimension vector and then I used one layer of LSTM with having 1024 units of cells and finally converted into vocab size.  
As target sequences are characters so I used sparse categorical crossentropy loss for training purpose.
Finally, I generated text by taking prompt statement as an input.
## Word-Wise Text Generation
Here I have built the text generator model by using pretrained embedding layer and Recurrent Long Short Term Memory Network by word wise training the network which also takes sequences of words up to sequence of length 50 and it predicted the next word of that sequence.
In this model I used Glove vectors for word representation in which embedding is a featurized vector representation of a word. In this representation the words related to each other remains close. So, it becomes easy for the network to generate next word after seeing preceding words in this representation and then I have used two layers of LSTM with having 400 units of cells and then converted into vocab size.
For training the text generator model the loss I used is categorical crossentropy and then finally, I generated text by using statement as an input. 
## Quality Measure
BLEU is the most widely used metric for text generation. Self-BLEU was introduced to evaluate just variety of sentences. It measures BLEU score for each generated sentence by considering other generated sentences as reference. By averaging these BLEU scores (obtained for generated sentences), a metric that is called Self-BLEU is achieved where its lower values shows more diversity.
## Quality Improved
Quality of text generation can be increased by using word-wise text generation instead of character-wise text generation because in character wise training I found spelling of some generated words are wrong and some sentences are not meaningful. For further quality improved which can be done by using BERT vectors for word representation.
By increasing the number of layers of LSTM along with increasing the units of LSTM up to 700 then the quality of output will increase.
By using Bi-Directional RNNs (BRNNs) instead of using RNN’s and by using attention model the quality will further enhance. 




