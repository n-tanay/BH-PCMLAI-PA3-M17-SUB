# BH-PCMLAI-PA3-M17 - Comparing Classifiers

Link to Notebook: https://github.com/n-tanay/BH-PCMLAI-PA3-M17-SUB/blob/main/BH-PCMLAI-PA3-M17-Comparing-Classifiers.ipynb

## Findings

### When evaluating model performance, it’s important to consider both accuracy and F1-score.

- Accuracy measures the proportion of correct predictions. It is a straightforward metric but may be misleading if there is a class imbalance (e.g., one group is much larger than the other).
- F1-Score balances precision (the proportion of correct positive predictions) and recall (the proportion of actual positives identified correctly). It is especially useful when the costs of false positives and false negatives are different or when class distribution is imbalanced.
- In this case, since the goal is to predict customer behavior (a potentially imbalanced task), both metrics were evaluated.

F1-Score Performance:
- Logistic Regression: Achieved an F1-score of 0.874, indicating balanced performance between precision and recall
- k-Nearest Neighbors (kNN): Performed best on F1-score (0.945), suggesting high precision and recall, but accuracy is lower on unseen data, indicating possible overfitting
- Decision Tree: Achieved the highest F1-score (0.967), which indicates very high performance in predicting both classes. However, the risk of overfitting suggests that this high score may not generalize well to new data
- SVM: Had an F1-score of 0.908, showing balanced performance, though the computational cost of training this model was high.

### Key Insights
1. Decision Tree’s Initial Performance:
- Training Accuracy: 1.000 (perfect)
- Test Accuracy: 0.887
- Insight: While the Decision Tree fits perfectly to the training data, its test accuracy is significantly lower, indicating overfitting. Hyperparameter tuning can help adjust its complexity for better generalization.
2. Logistic Regression as a Baseline Model:
- Training Accuracy: 0.873
- Test Accuracy: 0.863
- Insight: The model shows a balanced performance with a small gap between train and test accuracy, indicating strong generalization. It’s a reliable baseline model with low computational costs.
3. SVM’s Computational Cost:
- Training Accuracy: 0.913
- Test Accuracy: 0.860
- Insight: The SVM performs well on both training and test data, but its high computational time (271.79 seconds) makes it less suitable for quick predictions without clear performance benefits over simpler models like Logistic Regression.
4. KNN’s Performance:
- Training Accuracy: 0.950
- Test Accuracy: 0.858
- Insight: The kNN model is computationally inexpensive, but its performance drops significantly when predicting new data. This hints at overfitting and sensitivity to parameter choices.

AUC-ROC Performance Recap:
- Logistic Regression and SVM: Both had high AUC-ROC scores of 0.94, showing strong ability to differentiate between customers who will and will not subscribe.
- kNN: AUC-ROC of 0.85, suggesting decent discrimination but less effective than the Logistic Regression and SVM.
- Decision Tree: AUC-ROC of 0.72, indicating poorer performance in distinguishing between classes compared to other models.

### Model Performance in Business Context

- Logistic Regression: Achieved an AUC-ROC of 0.94 and an F1-score of 0.874, showing strong predictive power and a good balance between accurately identifying both subscribers and non-subscribers. Its low computational cost makes it practical for quick and frequent predictions, making it a reliable choice for helping the bank target the right customers efficiently.
- k-Nearest Neighbors (kNN): Though it scored well on F1-score (0.945), the model’s lower accuracy on new data suggests that while it may recognize patterns in past customer behavior, it may not generalize well to future campaigns. This limits its practical use for the bank’s goal of targeting new customers.
- Decision Tree: Despite its high training performance (F1-score of 0.967), it may overfit to the specifics of past customer data, reducing its ability to effectively predict future customer behavior. However, with regular tuning, it could still offer value by capturing complex patterns in customer responses.
- SVM: Comparable to Logistic Regression in terms of predictive power (AUC-ROC of 0.94), but with high computational costs. This makes it less suitable for the bank’s needs unless computational efficiency is not a concern.

### Implications for the Bank’s Marketing Strategy

1. Targeting High-Probability Customers:
    - Logistic Regression provides accurate, quick predictions, allowing the bank to identify and prioritize customers most likely to subscribe to a term deposit. This enables targeted marketing efforts, reducing costs and improving campaign effectiveness.
2. Optimizing Resources Based on Predictions:
    - Using the model predictions, the bank can allocate resources effectively:
    - High-likelihood customers can be sent personalized and resource-intensive campaigns.
    - Low-likelihood customers can receive lighter marketing or be deprioritized, saving costs.
3. Regular Model Updates for Accuracy:
    - As customer behavior and market trends change, updating and retraining the model will keep predictions accurate, ensuring that the bank continues to optimize marketing efforts for maximum impact.

### Next Steps and Recommendations for the Bank

1. Deploy Logistic Regression as the Primary Model:
    - Given its strong performance and ease of use, it should be used to generate real-time customer predictions for term deposit campaigns.
2. Monitor Model Performance and Customer Feedback:
    - Regularly evaluate the model’s predictions against actual outcomes, fine-tuning the model as needed to maintain its accuracy and business value.
3. Incorporate Model Insights into Marketing Strategies:
    - Design specific campaigns for the customer segments predicted to have a high likelihood of subscribing. This could mean offering personalized benefits, improving the timing of marketing outreach, or tailoring messages to customer preferences.
4. Reassess Model Choices Based on Resources and Needs:
    - If more computational resources become available, consider SVM for potentially more nuanced predictions. If interpretability or understanding customer decision paths is important, a tuned Decision Tree might offer deeper insights.

### Conclusion

By implementing a well-performing predictive model like Logistic Regression, the bank can effectively streamline its marketing campaigns, leading to better customer targeting and increased subscriptions for term deposits. This ultimately boosts the efficiency of promotional efforts, reduces marketing costs, and maximizes customer acquisition.