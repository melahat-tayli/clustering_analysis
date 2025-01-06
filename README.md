
# Clustering Social Media Posts into Depressed and Normal Categories  
 

## 0.1 About the Dataset and Hypothesis Statement  

### 0.1.1 Dataset Description  
The dataset is sourced from Kaggle and contains text collected from various social media platforms such as Facebook and Twitter. It consists of two columns:  
- **Text**: Posts related to mental health.  
- **Labels**: Emotional state of the post.  
  - **1**: Depression-related text.  
  - **0**: Normal mood text.  

### 0.1.2 Hypothesis Statement  
Social media posts reflect people’s mental health states. By analyzing the text, I hypothesize that posts can be clustered into two categories: **depressed** or **normal**.  

---

## 0.2 Exploratory Data Analysis  

- Depressed texts often include words like *anxiety*, *heart*, *nervous*, and *restless*.  
- Normal texts rarely feature these terms.  

### 0.2.1 Observations on Dataset  
- **Number of Depressed Text Entries**: 730  
- **Number of Normal Text Entries**: 6,230  
  - The dataset is imbalanced, with a significantly higher proportion of normal text entries.  

### 0.2.2 Sentence Count  
- Most texts (>5,000) consist of only **1 sentence**, while others have up to **7 sentences**.  
- The distribution of sentence counts is similar for both depressed and normal texts.  

### 0.2.3 Word Count  
- Depressed text entries generally have a **lower word count** compared to normal texts, indicating that depressed posts tend to be shorter.  

---

## 0.3 Text Representation Approaches  

To analyze the data numerically, the following techniques were employed:  

1. **TF-IDF (Term Frequency-Inverse Document Frequency)**:  
   - Highlights the most important words by weighting terms based on their uniqueness.  
   - When combined with PCA, it reveals latent semantic information on principal components.  

2. **Vector Representations via spaCy**:  
   - Pre-trained word embeddings from spaCy capture the semantic meaning of words.  
   - Suitable for clustering and sentiment analysis, as it represents entire sentences or documents.  


### 0.3.1 Dimensionality Reduction  
- **PCA (Principal Component Analysis)** and **LDA (Linear Discriminant Analysis)** were used to:  
  - Reduce the dimensionality of numerical representations.  
  - Visualize clusters in a lower-dimensional space.  

### 0.3.2 Clustering Algorithms  
Clustering was applied to both original and reduced representations using:  
1. **K-Means**  
2. **K-Medoids**  
3. **Gaussian Mixture Models (GMM)**  

---

## 0.4 Results and Challenges  

### 0.4.1 Key Findings  
- Clustering methods failed to correlate effectively with the true labels.  
- Low scores on **Adjusted Rand Index (ARI)** and **Normalized Mutual Information (NMI)** revealed poor performance.  

### 0.4.2 Challenges  
My hypothesis was that social media posts reflect mental health states and can be categorized into depressed or healthy based on text analysis. While exploratory analysis highlighted distinct linguistic patterns in depressed texts (e.g., frequent use of words like *anxiety*, *restless*, etc.), clustering methods struggled to effectively separate the categories.  

Possible reasons include:  
- The random nature of clustering algorithms.  
- Class imbalance between depressed and normal text entries.  
- The **non-spherical structure** of the data, which clustering algorithms struggled to model.  
