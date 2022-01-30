# A-B-Testing-Free-Trial-Screener-


### Data Source

- This project simulated experiment results by adding random noise to original data from [Udacity: A/B Testing](https://docs.google.com/spreadsheets/d/1Mu5u9GrybDdska-ljPXyBjTpdZIUev_6i7t4LRDfXM8/edit#gid=0).


### Experiment Overview: Free Trial Screener
At the time of this experiment, Udacity courses currently have two options on the course overview page: “start free trial,” and “access course materials.” If the student clicks “start free trial,” they will be asked to enter their credit card information, and then they will be enrolled in a free trial for the paid version of the course. After 14 days, they will automatically be charged unless they cancel first. If the student clicks “access course materials,” they will be able to view the videos and take the quizzes for free, but they will not receive coaching support or a verified certificate, and they will not submit their final project for feedback.
In the experiment, Udacity tested a change where if the student clicked “start free trial,” they were asked how much time they had available to devote to the course. If the student indicated five or more hours per week, they would be taken through the checkout process as usual. If they showed fewer than 5 hours per week, a message would appear indicating that Udacity courses usually require a more significant time commitment for successful completion, and suggesting that the student might like to access the course materials for free. At this point, the student would have the option to continue enrolling in the free trial or access the course materials for free instead. This screenshot shows what this experiment looks like.

![image](https://user-images.githubusercontent.com/47337257/151720815-1fcf6ad3-5563-454b-b5c2-3f6082e85471.png)

### Experiment Setup
The primary aim of Udacity is to improve the overall student experience and improve coaches’ capacity to support students who are likely to complete the course.
- Null Hypothesis: This approach might not make a significant change and might not be effective in reducing the early Udacity course cancellation.
- Alternative Hypothesis: This might reduce the number of frustrated students who left the free trial because they didn’t have enough time, without significantly reducing the number of students to continue past the free trial and eventually complete the course.

 Initial Hypothesis
The hypothesis was that this might set clearer expectations for students upfront, thus reducing the number of frustrated students who left the free trial because they didn't have enough time—without significantly reducing the number of students to continue past the free trial and eventually complete the course. If this hypothesis held true, Udacity could improve the overall student experience and improve coaches' capacity to support students who are likely to complete the course. (Provided by Udacity)

Based on the information above, we can set some initial hypothesis: (these are just iniinitial hypothesis and we will revise them further)

H0: the change has no effect on the number of students who enrol on the free trial.
H1: the change reduces the number of students who enrol on the free trial.

H0: the change has no effect on the number of students who leave the free trial.
H1: the change reduces the number of students who leave the free trial.

H0: the change has no effect on the probability of students who continue the free trial after 14 days.
H1: the change increases the probability of students who continue the free trial after 14 days.
(since we cannot say the number will be increased or decreased here, we use probability.)

Unit of Diversion (from Udacity): The unit of diversion is a cookie, although if the student enrolls in the free trial, they are tracked by user-id from that point forward. The same user-id cannot enroll in the free trial twice. For users that do not register, their user-id is not tracked in the experiment, even if they were signed in when they visited the course overview page.

### Experimental Design
#####Metric Choice
#####Invariant metrics
Invariant metrics are the ones used for sanity checks and will remain invariant throughout the experiment.
- Number of cookies: That is, number of unique cookies to view the course overview page.
- Number of clicks: That is, the number of unique cookies to click the “Start free trial” button (which happens before the free trial screener is a trigger).
- Click-through-probability: That is, number of unique cookies to click the “Start free trial” button divided by number of unique cookies to view the course overview page.
#####Evaluation Metrics
Evaluation metrics are the ones that we care about, the metrics that must be observed for consideration in the decision to launch the experiment.
- Gross conversion: That is, the number of user-ids to complete checkout and enroll in the free trial divided by the number of unique cookies to click the “Start free trial” button. (dmin= 0.01)
- Retention: That is, the number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by number of user-ids to complete checkout. (dmin=0.01)
- Net conversion: That is, number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by the number of unique cookies to click the “Start free trial” button. (dmin= 0.0075)
This graph below shows the process.
![image](https://user-images.githubusercontent.com/47337257/151720856-75e7e841-b22f-4ea5-952d-110a3aea779c.png)

Based on the metrics we choose and the initial hypothesis, we can revise our hypothesis.

H0: Gross Conversion(control) = Gross Conversion(treatment)
H1: Gross Conversion(control) != Gross Conversion(treatment)
H0: Retention(control) = Retention(treatment)
H1: Retention(control) != Retention(treatment)
H0: Net Conversion(control) = Net Conversion(treatment)
H1: Net Conversion(control) != Net Conversion(treatment)
## Reference

Context https://medium.com/@zhouyuchen999/a-b-testing-experiment-a-udacity-course-project-f958f7236278

https://arjan-hada.github.io/A/B-testing.html

https://nancyyanyu.github.io/posts/8fdfc10f/

Sample Size Calculator  https://www.evanmiller.org/ab-testing/sample-size.html

QuickCalcs: https://www.graphpad.com/quickcalcs/binomial1

A/B Testing - Udacity Course Final Project https://classroom.udacity.com/courses/ud257

A Summary of Udacity A/B Testing Course https://towardsdatascience.com/a-summary-of-udacity-a-b-testing-course-9ecc32dedbb1

A/B Testing (great source!)  https://rstudio-pubs-static.s3.amazonaws.com/201749_9fc280333a5c4f448687e1d99b9bdf76.html

The intuition behind A/B Testing https://towardsdatascience.com/the-intuition-behind-a-b-testing-a-primer-for-new-product-managers-6f21dee98533

How to split the traffic in an A/B Test https://towardsdatascience.com/smart-a-b-test-design-understanding-test-exposure-85ee44c897ba

Selecting A/B test metrics — A primer https://towardsdatascience.com/a-guide-for-selecting-an-appropriate-metric-for-your-a-b-test-9068cccb7fb

Which Metrics You Must Track While A/B Testing https://www.marketingoptimizer.com/blog/marketing-optimization/metrics-must-track-ab-testing/

Exit Rate vs. Bounce Rate https://support.google.com/analytics/answer/2525491?hl=en

