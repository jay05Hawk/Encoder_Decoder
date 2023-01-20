# Encoder_Decoder

$\color{blue}{\text{Encoder:}}$
Encoder models use only the encoder of a Transformer model. At each stage, the attention layers can access all the words in the initial sentence. These models are often characterized as having “bi-directional” attention, and are often called auto-encoding models.

Encoder models are best suited for tasks requiring an understanding of the full sentence, such as sentence classification, named entity recognition (and more generally word classification), and extractive question answering.

Representatives of this family of models include:

$\color{blue}{\text{ALBERT}}$
$\color{red}{\text{BERT}}$
$\color{blue}{\text{DistilBERT}}$
$\color{red}{\text{ELECTRA}}$
$\color{blue}{\text{RoBERTa}}$

$\color{blue}{\text{Decoder:}}$

Decoder models use only the decoder of a Transformer model. At each stage, for a given word the attention layers can only access the words positioned before it in the sentence. These models are often called auto-regressive models.

The pretraining of decoder models usually revolves around predicting the next word in the sentence.

These models are best suited for tasks involving text generation.

Representatives of this family of models include:    

$\color{blue}{\text{CTRL}}$
$\color{red}{\text{GPT}}$
$\color{blue}{\text{GPT-2}}$
$\color{red}{\text{Transformer XL}}$



## Encoder-Decoder model and implementation of RNN

Encoder-Decoder (encoding-decoding) is a very common model framework in deep learning. For example, auto-encoding of unsupervised algorithms is designed and trained with the structure of encoding-decoding; Is the encoding-decoding framework of CNN-RNN; for example, the neural network machine translation NMT model is often the LSTM-LSTM encoding-decoding framework. 

>Therefore, to be precise, Encoder-Decoder is not a specific model, but a kind of framework. Encoder and Decoder parts can be any text, voice, image, video data, and models can use CNN, RNN, BiRNN, LSTM, GRU, etc. So based on Encoder-Decoder, we can design a variety of application algorithms.

One of the most significant features of the Encoder-Decoder framework is that it is an End-to-End learning algorithm. Such models are often used in machine translation, such as translating French to English . Such a model is also called Sequence to Sequence learning. The so-called encoding is to convert the input sequence into a fixed-length vector and decoding is to convert the previously generated fixed vector into an output sequence.


## Applications

Encoder-Decoder is a model framework in the field of NLP. It is widely used for tasks such as machine translation and speech recognition.

>Machine translation, dialogue robot, poetry generation, code completion, article abstract (text-text)

"Text-text" is the most typical application, and the length of the input sequence and output sequence may be quite different.

Google's paper " <a href="https://papers.nips.cc/paper/5346-sequence-to-sequence-learning-with-neural-networks.pdf" target="_blank">Sequence to Sequence Learning with Neural Networks</a> " using Seq2Seq for machine translation.



### Speech recognition (audio-text)

Speech recognition also has strong sequence features, which is more suitable for the Encoder-Decoder model.

Google's paper " <a href="https://research.google/pubs/pub46169/" target="_blank">A Comparison of Sequence-to-Sequence Models for Speech Recognition</a> " using Seq2Seq for speech recognition




### Image description generation (Picture-Text)

Popularly speaking is "seeing pictures and speaking", the machine extracts the features of the pictures, and then expresses them in words. This application is a combination of computer vision and NLP.

Image description generated paper " <a href="https://arxiv.org/abs/1505.00487" target="_blank">Sequence to Sequence – Video to Text</a> "






## Encoder-Decoder flaws
As mentioned above, there is only one "vector c" between the Encoder and the Decoder, and the length of c is fixed.

For the sake of understanding, we analogize the process of "compression-decompression":

Compressing an 800x800 pixel image into 100KB, it looks relatively clear. Compress another 3000X3000 pixel image to 100KB and it looks blurry.



>**Encoder-Decoder is a similar problem: when the input information is too long, some information will be lost.**
