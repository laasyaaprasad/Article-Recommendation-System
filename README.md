# Article-Recommendation-System

# Goal : To develop a personalized article recommendation system ensures that readers stay interested and continue reading.

# Solution 

A  recommendation engine which is a function between users and items. The objective is to match each item with users through a recommendation engine which predicts which item a user will like the most. There are mainly 3 types of recommendation systems. 

* Content-Based Recommendation Systems: These systems suggest items similar to those a user has interacted with, leveraging item attributes and user preferences to identify patterns and recommend relevant content.

* Collaborative Filtering: This method predicts user preferences by analyzing past interactions, relying on user-item relationships and similarities among users or items, independent of content attributes.

* Hybrid Recommendation Systems: These combine content-based and collaborative filtering techniques to overcome limitations of individual methods, enhancing accuracy and robustness in recommendations.

<img width="600" alt="Screenshot 2024-12-20 at 2 15 15 PM" src="https://github.com/user-attachments/assets/9e0d3dbc-d0be-4c2c-8cf1-44d77d624351" />



The Matchmaking Formula (Objective Function) is a special formula to score how well each item matches each user’s tastes. This score is calculated for every possible user-item pairing. For each user, the engine looks at all the scores and picks the item with the highest score. 

If U = {users}, I = {items} then  F = Objective function and measures the usefulness of item I to user U, given by: F: U x I → R
Where R = {recommended items}.
For each user u, we want to choose the item i that maximizes the objective function:
u ∈ U, I' = argmax u(u, i) ​​

# System Architecture

<img width="1029" alt="Screenshot 2024-05-15 at 10 44 16 AM" src="https://github.com/laasyaaprasad/Article-Recommendation-System/assets/75083241/e1f42124-f1aa-4620-b1a0-7c075ab2e66a">

We started off with data preprocessing followed by algorithm selection. We have build context based, collaborative filtering and hybrid recommendation systems.The baseline selection was K means clustering.Then we implemented SVD on collaborative filtering and t-SNE Visualization followed by output analysis through metrics. 

Based on our EDA, We have created a scoring method called event type strength and assigned values to find the ground truth for recommendations. We have then mapped the event strength with each and every user by aggregating and creating a new column for it. Furthermore, in the third image, we have generated tags for each article for future recommendations and easier access.

Coming to dimensionality reduction we have used 3 techniques to reduce the number of features. We modified PCA clustering by using kernel PCA and got clear centroids and lower number of outliers. On employing tsne, we could see that the centroids aren’t very clear and there are many outliers. We could see clear clusters after applying K means. The word cloud is generated to get the most frequent occurrences of each word. We then proceeded with kernel PCA as it gave us better results.

# Content Based Filtering

In content-based filtering recommendation systems, item representation is paramount. Each item is characterized by a set of keywords, and the TF-IDF (Term Frequency-Inverse Document Frequency) method often serves as the backbone for assessing the significance of these keywords within the item's description. Concurrently, the user's profile is meticulously constructed, reflecting their past interactions and preferences. This profile mirrors the item representation, employing the same keywords to denote the user's inclination towards certain attributes or topics. Through sophisticated similarity calculations, typically leveraging cosine similarity or other measures, the system comapres and contrasts the user profile against item descriptions. This facilitates the identification of items that resonate closely with the user's preferences, offering tailored recommendations based on semantic correlations between item features and user interests. As the user engages with more content, their profile evolves, ensuring that recommendations remain finely attuned to their evolving tastes and preferences.

# Collaborative Filtering

Collaborative filtering, a cornerstone of recommendation systems, thrives on the vast troves of user data at its disposal. By meticulously analyzing user behavior, activities, and preferences, collaborative filtering discerns patterns and correlations that underpin user-item interactions. Its efficacy lies in predicting what users will like based on their affinity with similar users. Leveraging similarity metrics such as cosine similarity or Pearson correlation coefficient, the system identifies users with analogous preferences and propels recommendations grounded in collective wisdom. An inherent advantage of collaborative filtering is its adeptness at recommending intricate items such as articles or keywords, even in the absence of comprehensive understanding of the items themselves. 

# Hybrid Based Filtering

Hybrid filtering models are sophisticated models that integrate content-based and collaborative filtering methodologies. The scoring approach involves combining  the strengths of both techniques. Through analysis, these models calculate hybrid scores by multiplying the scores derived from content-based (CB) and collaborative filtering (CF) models. This hybrid scoring mechanism capitalizes on the complementary nature of CB and CF approaches, leveraging the rich insights garnered from item attributes and user behavior alike. By synthesizing these scores, the hybrid model encapsulates a holistic understanding of user preferences, thereby overcoming the limitations of standalone techniques. The resulting recommendations are finely calibrated, adeptly balancing the personalized precision of content-based analysis with the collective intelligence of collaborative filtering. 

# Evaluation Metrics 

When evaluating a recommendation model, the initial steps involve gathering data on the items a user has interacted with, and then creating a sample set of items the user hasn't engaged with yet. This dual approach allows for a thorough assessment of the model's performance in suggesting both familiar and new content, mimicking real-world scenarios. With these sets established, the evaluation proceeds to confirm if interacted items are indeed present within the top N recommended items, providing insight into the model's precision and recall.

Subsequently, the recommendation model undergoes rigorous evaluation using various performance metrics such as hits at 5 and 10, Mean Reciprocal Rank (MRR), and Normalized Discounted Cumulative Gain (NDCG). These metrics offer a comprehensive understanding of the model's effectiveness in recommending relevant items and prioritizing them accurately. By quantifying the model's performance across different dimensions, stakeholders can make informed decisions about further refinement and optimization efforts, ensuring the system continually evolves to meet user needs and preferences.

[Article Recommendation System.pdf](https://github.com/laasyaaprasad/Article-Recommendation-System/files/15323456/Article.Recommendation.System.pdf)







