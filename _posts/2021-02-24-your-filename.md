---
published: false
---
## Software-Engineering Chat-bot - Part 1

* **Title**: Experiences Building an Answer Bot for Gitter
* **Authors**: Ricardo Romero, Esteban Parra, Sonia Haiduc
* **Link**: [https://cpb-us-w2.wpmucdn.com/sites.udel.edu/dist/8/2570/files/2020/03/MSR20_Data.pdf](https://cpb-us-w2.wpmucdn.com/sites.udel.edu/dist/8/2570/files/2020/03/MSR20_Data.pdf)
* **Tags**: communication, chat, social media, team communication platforms, bot, Q&A, recommendation
* **Year**: 2020

# Summary

# What:

* They developed a bot that can automatically detect when a developer asks a technical question in a chat and leverages the information present in Q&A forums to provide the developer with possible answers to their question.
* They also develop a dataset to identify troubleshooting questions, which consist of 109,189 messages, and 1,000 manually label data.

# Motivation:
* Developers prefer to use real-time chating system to do their communications instead of asynchronous system like mailing list. 
* Study on conversation that developer had in a messaging platform from a large company indicated that half of message was about the technical issue (Q&A).
* Decrease a time needed to answer general questions(troubleshooting question).

# What
Here is an overview of GitterAns bot:


* Their first part is question detection (identifing wheather a question in troubleshoot or not).
	1. They read income messages.
    2. They do a preprocessing steps(lemmatization and stop words removal)
	4. Using tf-idf for feature representation.
	3. Finally, train Naïve Bayes, Random Forrest, and Stochastic Gradient Descent to detect questions.
   
* Second step is searching for possible answers.
* They Used Google CustomSearch API to search StackOverflow for semantically similar posts to the question.
	1. They use troubleshooting question as query. 
    2. Then used Google CustomSearch API with scope limited to SO to do their search.
    * In this way their utilized the power of google engine, instead of naïvely search in SO.

* GitterAns is able to find the correct answers only in about half of the cases.
	* It is critical to choose a proper query for information retrieval applications on software engineering data [18]
   




