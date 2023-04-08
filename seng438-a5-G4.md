**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:      | 4               |
| -------------- | --------------- |
| Student Names: | Rayyan Khalil   |
|                | Ammar Elzeftawy |
|                | David San Kim   |
|                | Eduardo Benetti |

# Introduction

The primary objective of this lab was to help students understand the evaluation of reliability and the utilization of tools like C-SFRAT and the Reliability Demonstration Chart. Moreover, the lab explored failure reliability growth testing, which facilitates the analysis of modifications made to a product over a specific duration. Lastly, the team also learned about the significance of failure data analysiss in identifying strategies to avoid failures. These ideas reinforced the concepts students had learned in our lectures and gave the team a clear understanding of the importance of reliability testing in software testing processes.

# Assessment Using Reliability Growth Testing

** for this part of the assignment, the C-SFRAT tool was not showing any covariates for any input data. During the demo, the TA also confirmed that our input data format was 100% right and that we were doing everything right, however under the covariates tab, it was always showing "None".
J5.DAT file was used, it was transformed into an excel file so that C-SFRAT can process it. **

The plot of the original data using the whole failure data range.
![WhatsApp Image 2023-03-30 at 3 43 52 PM](https://user-images.githubusercontent.com/86868318/228972993-023e2214-0ed0-4e24-b75d-f50326fc8ad9.jpeg)

Starting by selecting all the hazard functions to examine all possible models with the original plot of the data.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (1)](https://user-images.githubusercontent.com/86868318/228973002-1c7cc760-35ec-4963-b81a-5e8ee03cbb4b.jpeg)

Using the model comparison tab in the C-SFRAT tool, we sorted the rows in descending order of log-likelihood, to compare different models and to select the top 2 models by selecting the rows with the highest log-likelihood.
Using this approach, we decided that the 'S' and 'DW3' are the best models to use for our input data.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (2)](https://user-images.githubusercontent.com/86868318/228973012-fa120c47-977a-414e-a65b-b9afc6578a4b.jpeg)

The graph of 'S' and 'DW3' models with our original failure data.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (3)](https://user-images.githubusercontent.com/86868318/228973019-d2d33a56-05cd-4a5b-8b5d-1d8d44b6c302.jpeg)

The graph of 'S' model alone with our original failure data.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (4)](https://user-images.githubusercontent.com/86868318/228973027-a5559446-ea91-4f4c-ac80-fefd5a83ba44.jpeg)

The graph of 'DW3' model alone with our original failure data.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (5)](https://user-images.githubusercontent.com/86868318/228973039-b088c0ef-4b15-4943-a2b5-a7c3c5bff57a.jpeg)

Failure Intensity and Reliability graph using our original failure data and 2 predicted models from the 2 best models chosen above: 'S' and 'DW3'.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (6)](https://user-images.githubusercontent.com/86868318/228973046-5e638134-cea4-4654-869b-f3c6d6aad368.jpeg)

Reliability graph using our original failure data and predicted model using 'S' model.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (7)](https://user-images.githubusercontent.com/86868318/228973071-a255e4b6-5493-4548-ac31-7630f76e649d.jpeg)

Reliability graph using our original failure data and predicted model using 'DW3' model.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (8)](https://user-images.githubusercontent.com/86868318/228973103-16ec75b5-327c-43ea-9ad1-9847e6d99040.jpeg)

Using the reliability graph obtained and the our data, we have that 367 cumulative failure counts in 73 weeks, which gives us a failure rate around 5.02.
We set a failure intensity target 3.00 (lower than failure rate) and we observe how each model predicts how and when we can reach this failure target.
![WhatsApp Image 2023-03-30 at 3 43 52 PM (10)](https://user-images.githubusercontent.com/86868318/228973132-16a11622-36a6-46d7-bcc6-5f5638d44b5d.jpeg)

# Assessment Using Reliability Demonstration Chart

3 plots for MTTFmin, twice, and half of it for test data:
![image](https://user-images.githubusercontent.com/90352983/229210719-8e6bad54-6088-4d3c-9da0-5b1fa681f777.png)

In order to decide the MTTFmin, there were a few steps to complete. Firstly, our group converted the data given in DAT to a text file. Moreover, the value for the Discrimination Ratio (γ), Consumer Risk (β), and Developer Risk(α) were tried with some what-if scenarios for our system under test and the results were the following:

For Discrimination Ratio = 2, Consumer Risk = 0.1, and Developer Risk = 0.1:
![image](https://user-images.githubusercontent.com/90352983/229032428-c378cda8-555c-40e9-8be9-64be698e63b3.png)

For Discrimination Ratio = 1.2, Consumer Risk = 0.1, and Developer Risk = 0.1:
![image](https://user-images.githubusercontent.com/90352983/229032491-ac362e1c-9c36-4f9c-bedf-14dc73ce6122.png)

For Discrimination Ratio = 2, Consumer Risk = 0.3, and Developer Risk = 0.2:
![image](https://user-images.githubusercontent.com/90352983/229032552-ab23b223-e632-4a7b-bae7-7e18b6f358eb.png)

For Discrimination Ratio = 2, Consumer Risk = 0.2, and Developer Risk = 0.5:
![image](https://user-images.githubusercontent.com/90352983/229032591-e00df59e-f273-4622-9761-3aa69424cbcd.png)

And finally, for Discrimination Ratio = 2, Consumer Risk = 0.8, and Developer Risk = 0.1:
![image](https://user-images.githubusercontent.com/90352983/229207738-b402d49a-baa0-49ca-938d-b3529ed50a4c.png)

The last image was decided as our final graph with MTTFmin = 1.0. This MTTFmin was used since the blue Failure Data point crossed the Accept region of our graph. It is also important to note that the Discrimination Ratio was kept above 1 so that the estimation of failure intensity had an acceptable error, and that both Consumer Risk and Developer Risk had to be a value between 0 and 1.

There are several benefits to utilizing RDC as an analytical approach for determining the reliability of a system. One such advantage is its versatility, as it can be applied to various systems with differing characteristics. Additionally, RDC is an efficient method that saves both time and money in the analysis of a system's relibiality. Moreover, the ability to conduct experimentation with varying levels of confidence and what-if scenarios is a straightforward process.
However, despite its usefulness, RDC does have certain limitations. One such limitation is the inability to calculate precise quantitative values for the reliability of a system. Furthermore, RDC can only indicate whether the system under test is deemed acceptable or unacceptable without providing a specific reliability estimate.

# Comparison of Results
In Part 1 of our analysis, we aimed to predict the reliability of the system in order to determine an acceptable failure rate target of 3. This was achieved by analyzing the system's failure rate history, as well as conducting various tests and simulations to assess its performance under different conditions. Based on these findings, we were able to set a failure rate target of 3, which is considered an acceptable level of reliability for the system.

In Part 2 of our analysis, we used a Reliability Demonstration Test (RDT) to further evaluate the system's reliability. Specifically, we used the RDT to estimate the Mean Time to Failure (MTTFmin), which is the expected number of failures that will occur before a specified time period (in this case, one acceptable failure). Our analysis found that the MTTFmin for the system was 1.0 acceptable failures, which translates to a failure rate of around 0.005. This result indicates that the system is capable of achieving the acceptable failure rate target of 3, and suggests that it is operating at a high level of reliability.

# Discussion on Similarity and Differences of the Two Techniques

Reliablity growth testing and reliability demonstration chart are two approaches used in software engineering tro improve software reliability. Both methods involve testing software to evaluate its reliability and identify defect. Additionally, both use stattistical analysis to determine the software's reliability. However, there are notable differences between the two. Reliability growth testing is an iterative process that involves testing the software repeatedly and tracking the number of defects found and resolved over time. Its goal is to identify and fix defects early in the development process to improve software reliability. Reliability demonstration chart, on the other hand, is a graphical representation of the testing process that show the accumulated number of test cases executed, the number of defects found, and the expected number of defects remaining. Its goal is to demonstrate that the software meets a specific reliability target before it is released. Reliability growth testing is typically conducted during development phase, while reliability demonstration testing is conducted at the end of the development phase, before the software is released. Thus, reliability growth testing is focused on improving software reliability, while reliability demonstration testing is focused on demonstrating that the software meets the specified reliability requyirements.

# How the team work/effort was divided and managed

It varied throughout the assignment journey. Initially, everyone did the setup on their own machines, which led to incompatibility and OS issues. Due to that, we decided to split the group into pairs to work on separately, with that the team was able to proceed with the assignment. However, whenever there was an issues where one of the pairs got stuck due to system errors or any sort of block, the team reunited to analyze it faster and more effieciently. Lastly, the report was a time where all teams members contributed to insert all the learnings and work each one did on the assignment. Overall the division varied, but it was evenly distributed among all team member. At the end, the team was able to deliver a high quality report alongisde a interesting experience to learn about software reliability testing.

# Difficulties encountered, challenges overcome, and lessons learned

There were mainly two obstacles through out the development of the lab assignment. Firstly, the incompatibility with some machines made it hard to have all group members working on separate tasks at the same time. To tackle that issue, we divided the team into two pairs to work more efficiently, while one group member analyzed the data, the other inputted the information into the required applications to be correctly processed. Even having this division, all group members participated actively on the discussions about the routes that the team should take and ways to work more efficiently. The second biggest challenge was to setup the softwares and given data into the machines. Instructions were not very clear and detailed for us, since we didnot have any background on how to use them, so it took some time for us to get used to the software and its functionalities. To tackle that issue, the team joined to work on together rather than in pairs, its was effectively, yet it still took us a long time to realize some very simple issues we were having due to lack of documentation.

# Comments/feedback on the lab itself

This lab was interesting to get a practical sense of software test reliability, moving away from slides and actually runnning test helps a lot to throughly understand the content. However, it would be better to use more modern and recently developed tools rather than the ones used for this assignment. The incompatibility with different OSs and other version-related problems should be fized by using more recent applications. Additionally, that process costed a lot of time to work on the assignment since we could not have everyone working separately on different parts of the assignment. Lastly, please add more detailed instructions to use the tools. Since is was something new for all students, the learning curve is very steep and time consuming. I believe having videos and proper documentation can help future students have a insightfull and efficient learning process (having a video to go through the application would be a lot better).
