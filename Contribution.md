# Personal Contribution

## What did you personally contribute to the most?

I personally contributed most to K-Means and Segmentation. 
Specifically, my contributions in this area include:
- Writing the code to for k-means calculations and segmentation
- Evaluating and choosing input features for the k-means
- Evaluating the quality of the segmentation via multiple metrics

## What is one decision or approach you personally advocated for and why?

One decision that I personally advocated for was using three segments in our final segmentation. Based on metrics used to evaluate the segmentation, arguments could be made for four segments over three. I advocated for three segments primarily because of interpretability. Scores were within acceptable ranges for both segmentations, however threee segments were easier to interpret than four due to the drastic difference between the means of the most relevant features to our model.

## What are one or two lessons learned from the case competition, and what would you add on or improve in your case if you had more time?

### **Lessons:**
- I have learned about how great of an effect parameters can have on a model. Seeing how different values for different metrics can be obtained from the same datset has made me want to learn all about the specifics of parameters and their specific effects.
- I have learned that teamwork when writing code can be very difficult, especially without using any resources that allow us to sync our code and compare in real time. Our project would have greatly benefitted from an IDE to allow us to write code and compare more frequently.

### **Potential Additions/Improvements:**
- I would look further into feature engineering in order to improve our model. I think that our dataaset has the potential for great feature engineering which would greatly improve our model. Specifically, I believe that we could such as further evaluate numeric variables and possibly consolidate and remove some of them in the interest of eliminating extra noise. For example, `tenure_mo`, `total_billed`, and `monthly_fee` are highly correlated and all provide the same information in different formats. 
- I would explore the potential for model improvement via balancing the target variable distribution. The targe variable is heaveily skewed towards the negative, which limits the potential for the final model to predict with the highest accuracy. Introducing synthetically generated data via SMOTE or another method could drastically improve the model.

