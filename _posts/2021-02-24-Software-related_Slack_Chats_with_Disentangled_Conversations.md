---
published: false
---
## Software-Engineering Chat-bot - Part 1

* **Title**: Software-related Slack Chats with Disentangled Conversations
* **Authors**: Preetha Chatterjee, Kostadin Damevski, Nicholas A. Kraft, Lori Pollock
* **Link**: [https://cpb-us-w2.wpmucdn.com/sites.udel.edu/dist/8/2570/files/2020/03/MSR20_Data.pdf](https://cpb-us-w2.wpmucdn.com/sites.udel.edu/dist/8/2570/files/2020/03/MSR20_Data.pdf)
* **Tags**: online software developer chats, chat disentanglement, chat-bot
* **Year**: 

# Summary


# What:
* They created dataset from developers' conversation on Slack channel.
* Their definition -> conversation = question followed by a discussion.
* Their dataset consist of 38,955 conversations, 437,893 utterances, contributed by 12,171 users.
# Motivation
* Introductory study on Slack conversations showed that Slack converstaion(and possibly conversations over other online chat services) contain valuable informations which could be used to improve variety of software maintenance tools. 
	* Informations: Code or Api Descriptions, programming practices, casue of common error and bugs[9,11]. 
    * 
	* Previously, emails, bug reports, tutorial, Q&A forumes have been utilized for this purpose. 
    
# Challenges:
Mining and extracting useful information from this kinda source can be challenging.

Since:
    * There is no pre-defined structure for sending a message.
    * Each conversation can contain different number of utterances.
    * The number of messages are not fixed( or there is not any pre-defined range).
    * Each conversation can contain many question and answer!
    
    
# How

* They used a modified version of Elsner and Charniak’s algorithm for chat chat disentanglement.
* Elsner and Charniak's method was developed based on #Linux IRC channel.
* Elsner and Chrniak's method:
	* supervised model based on a set of features between pairs of chat messages that occur within a window of time of each other.
    * The features include: 
    	* the elapsed time between the message pair
        * whether the speaker in the two messages is the same
        * occurrence of similar words, use of cue words (e.g., hello, hi, yes, no)
        * the use of technical jargon, among others (technical jargon = technical words/expressions) . 
	* Their modification was about time window. They consider messages occurred less than (1.518) seconds prior to it, or is within the last 5 utterances observed in the channel.
	* They also add Slack specific feature(e.g., outer link, code snippets), and features corresponding to gratitude.
    * Elsner and Chrniak: F1 0.66
    * Enhanced Elsner and Chrniak: F1 0.80
    * **Since during the process of creating the gold set of disentangled chat conversations annotators can disagree whether a new conversation branches off from the original or not, micro-averaged F-measure is considered more appropriate than the standard F-measure [14]**
* They extract their dataset from python, clojure, elm community in Slack.
* The overview of their procedure is as below: 

![Screen Shot 2021-02-24 at 4.59.28 PM.png]({{site.baseurl}}/_posts/Screen Shot 2021-02-24 at 4.59.28 PM.png)

* For selecting data, they utilized Slack channels which have a Q&A format from three differnt communities. Channels are: pythondev#help, clojurians#clojure, elmlang#beginners, and elmlang#general. These channels are public.
* For collecting data they incrementally downloaded conversations in channels from July 2017 to Jun 2019.
* They cleaned conversation(e.g., removing joining message)
* They obfuscated username for privacy purpose.
* To use disentanglement methods they manually annotated 500 messages from each slack channel.

# Future works:
Theirs:

* Use this dataset like Q&A froums for task such as training a IDE recommendation system, recommendation of APIs, automatic generation of comments for source code, and in building thesauri and knowledge graphs of software-specific terms and commonly-used terms in software engineering.
* It can be used in several mining-based software engineering tools.
* It contain valuable opinions or recommendations.
* Can use to identify ‘hot’ topics of discussion in a program- ming community [31], and understand common challenges and misconceptions among developers [5].
* **Software Engineering Chat-bots.**
