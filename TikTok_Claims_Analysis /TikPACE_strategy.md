# Course Two: Get Started with Python

## Instructions

Use this PACE strategy document to record decisions and reflections as you work through this end-of-course project. You can use this document as a guide to consider your responses and reflections at different stages of the data analytical process. Additionally, the PACE strategy documents can be used as a resource when working on future projects.

## Course Project Recap

Regardless of which track you have chosen to complete, your goals for this project are:
* Complete the questions in the Course 2 PACE strategy document.
* Answer the questions in the Jupyter notebook project file.
* Complete coding prep work on the project’s Jupyter notebook.
* Summarize the column Dtypes.
* Communicate important findings in the form of an executive summary.

## Relevant Interview Questions

Completing the end-of-course project will help you respond to these types of questions that are often asked during the interview process:
* Describe the steps you would take to clean and transform an unstructured data set.
* What specific things might you look for as part of your cleaning process?
* What are some of the outliers, anomalies, or unusual things you might look for in the data cleaning process that might impact analyses or ability to create insights?

---

## Reference Guide

This project has three tasks; the stages of PACE are incorporated across those tasks as follows:
* **Task 1:** Frame the problem
* **Task 2:** Build dataframe
* **Task 3:** Understand the data

---

## Data Project Questions & Considerations

### PACE: Plan Stage

**How can you best prepare to understand and organize the provided information?**
The best way to prepare is to perform an initial data inspection using pandas functions like `.head()`, `.info()`, and `.describe()`.

**What follow-along and self-review codebooks will help you perform this work?**
A data dictionary to define columns and project documentation to clarify business goals would be most helpful.

**What are some additional activities a resourceful learner would perform before starting to code?**
Before coding, it's essential to clarify the primary business question, form initial hypotheses, and identify key variables like the target variable (claim_status).

---

### PACE: Analyze Stage

**Will the available information be sufficient to achieve the goal based on your intuition and the analysis of the variables?**
Yes, the information is sufficient because there are clear, consistent differences in engagement metrics between "claim" and "opinion" videos, making them valuable for a model.

**How would you build summary dataframe statistics and assess the min and max range of the data?**
I would use the `data.describe()` method in pandas to efficiently generate summary statistics, including the min and max range for all numerical columns.

**Do the averages of any of the data variables look unusual? Can you describe the interval data?**
Yes, averages for engagement metrics are unusual. "Claim" videos have about 100 times more views than "opinion" videos. Also, the mean for metrics like view count is much higher than the median, indicating the presence of outliers.

---

### PACE: Construct Stage

**Note:** The Construct stage does not apply to this workflow. The PACE framework can be adapted to fit the specific requirements of any project.

---

### PACE: Execute Stage

**Given your current knowledge of the data, what would you initially recommend to your manager to investigate further prior to performing exploratory data analysis?**
I would recommend investigating two things:
1.  Why claim videos get so much more engagement.
2.  The relationship between banned authors and higher engagement metrics.

**What data initially presents as containing anomalies?**
The engagement columns (video_view_count, video_like_count, video_share_count) present anomalies, evidenced by the large gap between their mean and median values, which suggests outliers.

**What additional types of data could strengthen this dataset?**
The dataset could be strengthened by adding data like video topics, author-level details (e.g., follower count), and timestamps for when videos were posted.
