# Text generation tool for GPT training
This is a part of my GPT-based research project. The goal is to generate natual-lanugage-like text
for training GPT networks. While there is A LOT of texts in the internet, like [the Pile](https://pile.eleuther.ai) or other
datasets, they are all for unsupervised learning for predicting the next/missing word in a text.
My goal is slightly different - i want to generate random texts which should look natural. I.e.
they should not irritate the human mind when trying to read them. For each text i want to generate
semantic questions, and for each question - possible answers and correct one.

This is similar to SQUAD dataset, but questions/answers will not match the parts of generated texts.
Here is an example of what I want to make:
```
Dog is black. Wolf is white. Giraffe is yellow.
What is the color of domestic animal?
Correct: Dog
(ChatGPT's answer): The color of a domestic animal can vary widely, depending on the breed or type of animal. Common colors for domestic animals include white, black, brown, gray, red, and yellow.
```
I.e. GPT-like text generator can generate good text, but semantically it can be wrong.

To solve that problems, we require many (A LOT) of changes in GPT. And the first one is to prepare
the new dataset. This repository is the place for Python-based code to generate that.

## Method
The method of text generation is based on using some static Language Model (LM), 
for example: [WordNet](https://wordnet.princeton.edu). I want to use word-semantic dependencies
to produce some random texts. These semantic dependencies will be then used to produce questions.
The next level here would be to reverse generate/extend LM based by using the smaller-trained
networks and reading some datasets (Wikipedia).

