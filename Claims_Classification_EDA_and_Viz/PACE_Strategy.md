## 📝 PACE Strategy Document - Course 3

---

### PACE: Plan Stage

| Question | Response |
| :--- | :--- |
| **What are the data columns and variables and which ones are most relevant to your deliverable?** | The data columns are: `#`, `claim_status`, `video_id`, `video_duration_sec`, `video_transcription_text`, `verified_status`, `author_ban_status`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`. The most relevant variables for predicting `claim_status` are likely the categorical variables (`verified_status`, `author_ban_status`) and the engagement count variables. |
| **What units are your variables in?** | `video_duration_sec` is in seconds. The count variables are in counts of views, likes, shares, downloads, and comments. |
| **What are your initial presumptions about the data that can inform your EDA, knowing you will need to confirm or deny with your future findings?** | I presume that videos posting **claims** might have different engagement characteristics (like view, like, or comment counts) compared to **opinion** videos. Also, the distribution of the count variables is likely **right-skewed**. |
| **Is there any missing or incomplete data?** | Yes, the output of `data.info()` shows that several columns have 19,084 non-null values, which is less than the total 19,382 entries, indicating **missing data**. |
| **Are all pieces of this dataset in the same format?** | The data types include `int64`, `object`, and `float64`. The count variables are currently `float64` but should likely be integers since they represent counts. |
| **Which EDA practices will be required to begin this project?** | Data **cleaning** (handling missing data, checking data types, checking for outliers), performing descriptive statistics, and generating **initial visualizations** (like box plots and histograms) will be required. |

---

### PACE: Analyze Stage

| Question | Response |
| :--- | :--- |
| **What steps need to be taken to perform EDA in the most effective way to achieve the project goal?** | Examine the data for missing values and duplicates. Analyze descriptive statistics and distributions of key numerical variables (checking for outliers). Analyze the distributions of categorical variables. Investigate correlations between variables, especially between the target variable (`claim_status`) and the engagement metrics. |
| **Do you need to add more data using the EDA practice of joining?** | No, based on the current problem and dataset, there is no indication that joining with other datasets is necessary at this stage. |
| **What type of structuring needs to be done to this dataset, such as filtering, sorting, etc.?** | Structuring involves handling **missing data** (likely dropping rows with missing values) and converting data types of count variables to **integers**. |
| **What initial assumptions do you have about the types of visualizations that might best be suited for the intended audience?** | **Box plots** and **histograms** are best suited for initial EDA to understand the distribution and identify outliers. For presenting results to stakeholders, simple visuals like **bar charts** and **pie charts** are good for showing counts and proportions. |

---

### PACE: Construct Stage

| Question | Response |
| :--- | :--- |
| **What data visualizations, machine learning algorithms, or other data outputs will need to be built in order to complete the project goals?** | Data visualizations include: Histograms and box plots of key variables; a histogram comparing claim counts to opinion counts, segmented by verification and ban status; a bar plot of median view counts by author ban status; and a pie chart of total views by claim status. The eventual goal is a predictive **machine learning model** for `claim_status`. |
| **What processes need to be performed in order to build the necessary data visualizations?** | Use Python packages like `matplotlib.pyplot` and `seaborn`. Data must be cleaned and structured first. For some plots (like the median view counts by ban status), **aggregation** (e.g., `groupby()` and `median()`) of the data is required. |
| **Which variables are most applicable for the visualizations in this data project?** | `claim_status`, `video_duration_sec`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, `video_comment_count`, `verified_status`, and `author_ban_status`. |
| **Going back to the Plan stage, how do you plan to deal with the missing data (if any)?** | Since the missing data only represents a small portion of the total entries (298 out of 19,382), the best approach is to **drop the rows** with missing values. |

---

### PACE: Execute Stage

| Question | Response |
| :--- | :--- |
| **What key insights emerged from your EDA and visualizations(s)?** | * The distribution of all engagement count variables is heavily **right-skewed**. * The vast majority of views (over 90%) are concentrated on videos classified as **claims**. * Unverified authors are the most numerous, but verified authors are **more likely** to post opinions. * Non-active authors (under review or banned) have a much **higher median view count** than active authors. * Videos classified as claims have a median view count ($\sim 500,000$) that is significantly higher than videos classified as opinions ($\sim 4,900$). |
| **What business and/or organizational recommendations do you propose based on the visualization(s) built?** | The high correlation between engagement metrics (especially `video_view_count`) and `claim_status` suggests that the model should prioritize these variables. Given that videos by non-active authors and videos classified as claims have significantly higher engagement, the organization should **focus resources** on these videos for review. |
| **Given what you know about the data and the visualizations you were using, what other questions could you research for the team?** | I want to further investigate **distinctive characteristics** that apply only to claims or only to opinions, considering other variables that might be helpful in understanding the data. This means exploring more deeply the relationship between the video's content (transcription text) and its claim status. |
| **How might you share these visualizations with different audiences?** | Visualizations should be clean, easily understandable, and accessible. The high-level findings, especially the total views by claim status (pie chart) and the median view counts by ban status (bar chart), are well-suited for an **executive summary** to share with management and clients. |
