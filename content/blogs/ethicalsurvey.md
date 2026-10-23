---
title: "Challenges and Ethical Concerns in Survey Design and Data Collection"
draft: false
author: "Rahman Ahmed"
tags:
  - Data Analysis
  - Ethics
  - Data
description: "A discussion on surveys and the ethical concerns that may arise in their design."
image: "https://moustascheman.github.io/MyPortfolio/images/skillspost.jpg"
date: 2026-10-16T10:00:00+00:00
---

# The Survey

Suppose for a given course, the students participating in this course are tasked with answering a survey upon its completion, one which they are to summarize their thoughts on the course and provide feedback. These students would have a short window of time to access a URL link to this survey and would also be required to login with their usernames and passwords to begin it. Once they've done so, the survey would prompt users for the name of the course that they are providing feedback for. It would, however, not do the same for their own names, with it instead stating that a user’s responses would be anonymous. 


![The Survey Question](https://moustascheman.github.io/MyPortfolio/images/blogs/surveyquestion.png)

The first question displayed in this survey would prompt users to answer whether “this course met all of the course objectives” and would allow participants to do so by selecting a number from zero to ten. These values would numerically represent their opinion on the matter, ranging from “strongly disagree” at zero to “strongly agree” at ten. 

Furthermore, it should be assumed that the results of this survey will be used by executive management to determine whether a course requires revision or redesigning. 

# The Problems with this Survey

While at first glance this survey may seem to be well designed, with its designers having clearly considered the privacy of its users, further analysis of it and the provided sample problem reveals that they both have a few pressing flaws in their design that should be addressed. In particular, one such concern is this survey’s promise of anonymity, one that is undermined by the requirement to login with their credentials to begin the questionnaire. Given this requirement, students may have difficulty believing in this promise of privacy, especially given the lack of transparency on how this anonymity is achieved as there are no other mentions within the survey of usernames or other personal identifiers being suppressed in the collected dataset. As such, a student may be reluctant to answer this survey and offer criticism out of fear that their responses may be traceable back to them, which in turn would hamper the efforts of any data scientists hoping to use the results of this survey to improve this course. 

However, even if personal identifiers such as username or student name are suppressed or not collected, the questions posed within this survey may still prove to be a privacy risk. Specifically, questions such as the sample question provided above may contain quasi-identifiers through the answers provided to them. A student who achieves a high grade in this course might consider its objectives met and thus be likely to answer highly for this question. Similarly, the opposite might occur for a student who performed poorly who may instead choose a ‘low’ value such as one or two. As such, the responses to this question and others like it could potentially be used by an instructor to reveal the identity of their answerers by cross-referencing these responses with the grades of their students. 

This concern also coincides with another regarding the biases of its participants. As mentioned earlier, students are likely to have their responses influenced by their academic performance within this course and as such they may provide biased data that should be accounted for when building a model based on this survey’s results. 

The sample question itself also has a few notable design flaws that may raise further ethical concerns. One such concern is the wording of the question itself, with it and the mention of “course objectives” being vague and as such likely to be misinterpreted by students answering them. As these objectives are not well-defined, answers to this question may vary and may lead to incorrect findings and inaccurate models. 

The 0-10 scale used within this question also poses similar problems with the eleven possible values being both too granular and vaguely defined to provide an accurate answer for this question. For example, participants may find it difficult to determine what the difference between a value of seven and a value of eight might be and as such these participants may find it difficult to answer correctly, further impacting the veracity of the survey’s findings. 

There are also several other ethical issues that may be present in the other questions in this survey. One such issue is the presence of additional quasi-identifiers in other additional questions that may impact the privacy of its subjects. While this first sample question does use a numeric scale ranging from 0-10, other questions may instead use textbox fields that allow students to type in detailed responses or comments. Doing so, however, would risk potentially identifying a participant, specifically by instructors or by anyone who may possess samples of their writing. By comparing these samples to their written responses, it would potentially be possible to discern the identity of this survey’s participants, even without any other potentially identifying information.  

Due to the presence of bias in the dataset returned by this survey, however, another ethical concern could also be just how these results would be used to inform future decisions by management. As the college intends to use this survey to decide whether to revise a course’s design or content, biased or inaccurate results motivated by poor performance may mislead executive management into making decisions that may negatively affect the content of this course. 

# Addressing these Concerns

Several steps can be taken to effectively address these issues. For example, to effectively anonymize a participant’s identity when answering questions just as the sample question, a data scientist can use various statistical disclosure limitation procedures to ensure k-anonymity. Specifically, grouping and aggregation can be used in these cases, specifically by aggregating scores together into various ranges. Furthermore, perturbance can be used to add noise to the dataset, ensuring that it is difficult to identify any specific participant.  

Similar techniques can be used for questions involving text fields, with the answers being potentially sorted into groups based on whether the feedback provided is ‘positive’ or ‘negative’. However, a better solution to protect the privacy of students would be to minimize the use of text fields and to prevent instructors from directly receiving this feedback. These instructors might instead receive a summary of these student comments, thus reducing the risk of them from being able to identify students based on their writing styles. 

To account for bias within the results of this survey, data processing methods such as reweighing can be used to adjust the data for the model. By accounting for a student’s expected grade, which the survey will ask for in a later question, data instances can be weighed to minimize the effects of biased responses. 

Furthermore, to improve the sample bias that may occur as a result of students being reluctant to answer this survey, instructors and course administrators may make the completion of this survey compulsory and assign it to their students as they would an assignment. Doing so would force students to answer this survey and thus would allow for more accurate results. 

To improve the accuracy of questions such as the sample question, the potential values can be aggregated further into 5 values rather than the current 11. These values would correspond to “strongly disagree”, “disagree”, “neither agree nor disagree”, “agree”, and “strongly agree” and would thus allow for more precise and accurate answers that better reflect a student’s actual opinion.  

Should Executive Management choose not to consider these recommendations and change the design of this survey, however, there are still various steps that can be taken to proceed ethically. Specifically, taking the steps mentioned above to summarize these collected surveys in a report would allow for the privacy of these students to be protected. Even if these questions are not changed or modified and the structure of the survey is not altered in any way, presenting these results in a report would allow neither Executive Management or the instructors running these courses to view the answers directly, and instead would only present the average or mean values for each question based on their numerical values. In doing so, it would prevent any single student from being reidentified, as no specific personal identifiers or quasi-identifiers would be presented directly to either of these two parties. 

# Conclusion

In summary, this survey and its design have various issues that raise ethical concern that may lead to negative outcomes such as students being reidentified or incorrect or misleading results being used to shape future policy by Executive Management. By modifying this survey and the questions within it, limiting the number of text-based questions, and using techniques such as aggregation, perturbance, and reweighing, a data scientist can address many of these ethical concerns and would be able to help protect the privacy of its data subjects while improving the accuracy of its findings. 