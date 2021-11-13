Ethan Park
CS 482
Fall 2019
Homework Assignment 5

This directory contains the following files:
+--	Sentiment-Analysis-AI
|	+--	corpusLong.txt
|	+--	README.md
|	+--	sentimentAnalysis.py


This directory contains a the files necessary to complete programming assignment 5 in python. It should contain all the files included in provided sample directory in addition to this README with only sentimentAnalysis.py being modified.

GetSentiment is now fully implemented and finds a score for the total sentiment of a sentence (a more negative score means the sentiment is more negative and the a more positive score means the sentiment is more positive). In order to find the total sentiment, it uses word2vec's similarity function to find the cosine similarity between each word of the sentence and the lists of good and bad words. Since the most simlar word will have the a cosine similarity closes to 1 (with a range 0 to 1) it finds the word with the highest cosine similarity. If this word is good, 5 points are added to the total sentiment. If this word is bad, 5 points are subtracted the total sentiment. After each word in the sentence is processed, the total sentiment is returned.

Main now calls GetSentiment for each sentence and outputs the total sentiment for each sentence. An explanation comparing the calculated sentiment my interpretation is also included for each sentence.

To run this program, python, nltk, and gensim must be installed:
pip install nltk
pip install gensim
chmod +x sentimentAnalysis.py


Once this is done enter:
./sentimentAnalysis.py
to run the program

No additional libraries were used that weren't already included in the sample directory.

The python script #!/usr/bin/env python (line 1) was added so that the program could be run without entering python in the terminal

Assumptions:
If the best matching good and bad word have the same cosine similarity, nothing is added to the total sentiment.

If the total sentiment is 0, the sentiment is neither positive nor negative (I added a case for it being neutral in my explanations).

NOTE:
On line 24
	for i in sent_tokenize(sent): 
was changed to 
	for i in sent_tokenize(sent.decode('utf-8')): 
as the original code gave me a unicode decoding error
