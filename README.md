# Understanding-IT-Employee-Turnover-with-LLM-Driven-Text-Analysis

> **Note:** This repository **only** provides a README (project overview & basic documentation).  
> **All source code is private** and not publicly accessible.

## Project Overview

High turnover rates among IT professionals remain a pressing concern for both companies and employees. This project aims to investigate the root causes behind frequent job changes in the tech sector by analyzing user-generated content on Reddit. We leverage a BERT-based text classification model to categorize Reddit posts and understand why IT professionals decide to leave their roles.

## Features

1. **Data Overview**  
   - I focused on posts from Reddit communities related to IT careers (e.g., `cscareerquestions`, `ITCareerQuestions`).
   - I identified potential turnover factors such as **burnout**, **low salary**, **toxic workplace**, etc.

2. **Text Analysis & Classification**  
   - Fine-tune a pre-trained model (e.g., `bert-base-uncased`) on labeled Reddit data to classify posts.
   - Address class imbalance via computed class weights to ensure minority classes receive adequate attention.

3. **Findings**  
   - **Burnout** and **work-life balance** consistently emerge as top turnover factors.
   - **Low salary** also plays a significant role, although more challenging to detect due to varied phrasing.
   - **Career stagnation** and **toxic workplace** appear less frequently and exhibit lower classification performance.

## Environment Setup

If you were to replicate the data analysis and modeling steps, you would need:

- **Python 3.8+**
- **praw** (for Reddit API access)
- **pandas**
- **matplotlib**
- **scikit-learn**
- **transformers**
- **torch**

However, the **full source code** for data gathering, preprocessing, and model training is **private** and **not** included in this repository.

## Data Collection Workflow (High-Level)

1. **Reddit API Setup**  
   - Configure `praw.Reddit(...)` with your own API credentials.

2. **Data Gathering**  
   - Search for relevant keywords (e.g., “burnout,” “low salary”) in chosen Subreddits.
   - Collect post titles, bodies, and a limited number of comments.

3. **Data Storage**  
   - Save scraped posts and metadata into CSV files for subsequent analysis.

## Model Training Workflow (High-Level)

1. **Preprocessing & Labeling**  
   - Merge title and body for each post.
   - Auto-label posts with keywords or assign them an “other” category if no keywords match.

2. **Train-Test Split**  
   - Divide the labeled data into training and testing sets (e.g., 80:20 ratio).

3. **Fine-Tuning BERT**  
   - Use `BertTokenizer` and `BertForSequenceClassification`.
   - Apply cross-entropy loss, optionally with class weights to handle imbalance.

4. **Evaluation**  
   - Evaluate on the test set using metrics such as Precision, Recall, and F1-score.
   - Plot confusion matrices for a detailed look at misclassifications.

## Results & Visualizations

- **Accuracy**  
  - The model typically achieves **88%–91%** accuracy on the test set, depending on hyperparameter choices and data balance.
- **Major Insights**  
  - “Burnout” and “work-life balance” categories are generally well-identified.
  - “Low salary” is moderately detected due to the wide range of possible expressions.
  - Less frequent categories (e.g., “career_stagnation,” “toxic_workplace”) show lower precision and recall.

## Access to the Private Code

This project’s **full source code (data scraping, scripts, fine-tuning details, etc.) is private**.  
If you have specific questions or need access for collaboration, please contact me directly.

## License

This repository and its documentation are provided **for reference only**.  
**All rights reserved.** You are not permitted to copy, distribute, or use any part of the private code without explicit permission.

---
