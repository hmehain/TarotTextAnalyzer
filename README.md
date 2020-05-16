# TarotTextAnalyzer
## Introduction
This program serves to analyze the descriptions for cards in a tarot deck. It attempts to identify the major themes present, and the similarity between different descriptions. The goal of this program is to determine how robust a card deck is in being able to describe the different aspects of reality. The aim is to develop a model for determining the relevant applications of a card deck. This will be helpful in identifying the limitations of a tarot deck, and prevent using a deck for a situation where none of the cards readily apply. Especially in the case of an oracle deck, the degree of repetitiveness can be determined, as well as areas that are lacking. Ideally, this tool could be used to develop decks that broaden the scope and application of tarot to incorporate different aspects and perspectives of reality.
## Functional Requirements
1.	Simple Java program with console output. 
2.	Find themes associated with each card.
<br>2.1.	Find the frequency of words in the text.
<br>2.2.	Uploads formatted txt file. 
<br>2.3.	Creates Arcana objects and assigns text to each Arcana card.
<br>2.4.	Identify possible keywords that represent main themes by finding least-used words that are abstract nouns. 
<br>2.5.	For each keyword, store the Arcana cards the word belongs to.
3.	Finds similar phrases, the number of times they repeat, and which cards they belong to. 
<br>3.1.	Store the place in the text where that word is found. 
<br>3.2.	Type in a keyword and return the Arcana cards it is found in.
<br>3.3.	Type in a keyword and find the other keywords found associated with that Arcana card.
<br>3.4.	Type in two or more keywords, and return either 1) the Arcana cards they are associated with, 2) only the cards they have in common.
<br>3.5.	Type in two keywords and find how many words are found between them. Create a data histogram with the median and quartile values. 
<br>3.6.	Search for phrases less than a set number of words that contains at least 2 of a set of at least 2 words, and show their variations. 

## Stages of Development
Each stage has it's own branch (i.e. Branch 1 will contain Stage 1)
### Stage 1
Simple Java program with console output. Finds the frequency of words in the text. (Requirements 1 & 2.1)
### Stage 2
Uploads formatted txt file. Creates Arcana objects and assigns text to each Arcana card. (Requirements 2.2 & 2.3)
### Stage 3
Try to identify possible keywords that represent main themes. Question: How do we do this? Ideas: find least-used words that are abstract nouns. (Requirement 2.4)
### Stage 4
For each keyword, store the Arcana cards the word belongs to. (Requirement 2.5)
### Stage 5
Store the place in the text where that word is found. (Requirement 3.1)
### Stage 6
Type in a keyword and return the Arcana cards it is found in. (Requirement 3.2)
### Stage 7
Type in a keyword and find the other keywords found associated with that Arcana card. (Requirement 3.3)
### Stage 8
Type in two or more keywords, and return either 1) the Arcana cards they are associated with, 2) only the cards they have in common. (Requirement 3.4)
### Stage 9
Type in two keywords and find how many words are found between them. Create a data histogram with the median and quartile values. (Requirement 3.5)
### Stage 10
Search for phrases less than a set number of words that contains at least 2 of a set of at least 2 words, and show their variations. (Requirement 3.6)

