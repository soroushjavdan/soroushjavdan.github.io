---
published: true
---

## Code Review Paper summary - Part 2

* **Title**: Do Explicit Review Strategies Improve Code Review Performance?
* **Authors**: Pavlína Wurzel Gonçalves, Enrico Fregnan, Tobias Baum, Kurt Schneider, Alberto Bacchelli
* **Link**: [https://sback.it/publications/msr2020rr.pdf](https://sback.it/publications/msr2020rr.pdf)
* **Tags**: Code Review, Effectiveness, Efficiency, Cognitive Load
* **Year**: 2020

# Summary

* What

	* Their goal is to test the effect of a guidance approach on review effectiveness and efficiency.
    
    * They designed an experiment which was consist of three code review tasks. They used three approaches for reviewing, reviewing without any guideline(no guidance), using a static review checklist ( they used Microsoft's checklists), and checking-list review strategy.
    
    * The checklist review strategy was designed to give guidance on how to perform a review. The review checklist was designed to provide an insight into what to look for in the review.
    
    * They investigated whether a checklist review strategy would provide any additional benefits compared to a static review checklist.
    
    * They made this comparison based on two metrics. Effectiveness means finding many of the contained defects and efficiency, which indicates how quickly the defects have been found.

	* They formulate their research in two research questions.
    	1. Does guidance in review lead to higher review effectiveness? and/or a higher review efficiency?
        2. Is the effect of guidance on code review mediated by a lower cognitive load?

* How

	* They took the guidance approach(no-guidance, checklist, or strategy) as the independent variable for both RQ1 and RQ2.
    
    * They used cognitive load as a mediator variable for the RQ2.
    
    * They conducted their study on three developer groups. The first group of developers did not receive any aid in the review(no guidance). The second group was presented with a checklist. They were required to identify defects using this checklist, but also any other defects that might appear. Finally, the third group received a checklist review strategy aid in the reviewing process. 
    
    * Checklist review strategy(strategy): It is somehow similar to the static checklist. It groups the static checklist item with respect to their relevant scopes(general items, classes, methods) and shows them in order. In other words, it only shows the meaningful items for the selected code chunk. The user must explicitly mark the items as checked before being able to proceed to the next item(s) in the review strategy.
    
    *  They asked participants to perform three code reviews clarifying that they only have to look for functional defects in the code. The first short code change contains three defects, while the others contain respectively nine and ten defects, and will show to participants in random orders.
    
    * Their experiment workflow:
    	1. Welcome page which contains general information about the experiment.
        2. Explanation which emphasizes that participants should focus on finding functional issues, and little explanation about the experiment tool.
        3. Three code review tasks. Participants were presented with three different code review tasks. At the end of each task, their mental load was measured by a questionnaire.
        4. If the participants were assigned to the checklist or checklist strategy group, they were presented with a questionnaire regarding the developed system's usability and quality.
        5. Asked developer whether there was any extraneous variable whose presence affected the experiment.
        6. Ending
    
* Analysis Plan

	* The reviewer who were not complete all the tasks or finished them less than 5 minutes were excluded.
    
    * TThey want to will conduct a One-way ANOVA to identify whether a difference between the three treatment groups exists and report the effect size !!!
    
    * They want to assess whether there is a partial or full mediation relation between cognitive load(as mediator) for the RQ2.  
    
   	* They want to present a correlation matrix table to assess potential covariance and relationships between examined variables.
    
* Result
	* No results have been presented in the pre-print version.

    
* Their primary contributions: Investigating the effect of adding strategy in code reviews. Also, they try to find a potential relationship between examined variables.
* I can't clearly tell their primary contributions(what I see) since there aren't any available results.

* Proposed feature work: Improving the checklist strategy to a more dynamic form. Maybe using a recommendation system to assign review with respect to developers' characteristics.
