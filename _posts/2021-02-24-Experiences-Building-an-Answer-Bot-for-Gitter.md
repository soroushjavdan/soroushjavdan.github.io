---
published: true
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
* Developers prefer to use a real-time chatting system to do their communications instead of an asynchronous method like a mailing list. 
* The study on conversations that the developers had using messaging platforms from a large company indicated that half of the message was about a technical issue (Q&A).
* Decrease the time needed to answer general questions(troubleshooting questions).

# What
Here is an overview of GitterAns bot:


* Their first part is question detection (identifying whether a question is troubleshoot or not).
  1. They read income messages.
  2. They did pre-processing steps(lemmatization and stop words removal)
  3. Using tf-idf for feature representation.
  4. Finally, train Naïve Bayes, Random Forrest, and Stochastic Gradient Descent to detect questions.
   
* The second step is searching for possible answers.
* They Used Google CustomSearch API to search StackOverflow for semantically similar posts to the question.
	1. They use troubleshooting questions as a query. 
	2. Then used Google CustomSearch API with a scope limited to SO to do their search.
	* In this way, they utilized the power of the google engine instead of naïvely search in SO.

* The GitterAns is able to find the correct answers only in about half of the cases.
	* It is critical to choose a proper query for information retrieval applications on software engineering data [18]
    * Using whole troubleshooting questions can present too much noise! 
	* They removed queries noise and just used exact error msg (e.g., Module did not self-register on bcrypt Module), and it was shown that it could boost the result.

* GitHub Issues, personal e-mail, Gitter, Twitter, and mailing lists are the five most popular communication channels currently used in open source development. **Slack was found to be eighth in terms** 

* All elements justifying the made decisions in the message constitute **rationale**(rational message).

# Future work

* Theirs:
	1. Remove the noise from messages containing troubleshooting questions
	2. Improving the classification of messages.
	3. Perform a large-scale evaluation/involve real developers in the evaluation.
* Mine:
	1. Extract tags and search question based on them.
	2. Develop a bot to find a question inside the channel from the previous msg (if possiblle)
