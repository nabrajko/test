# Housing Pricing Analysis for New York City

## Project Objective and Goals
**Objective:**  
The objective of this project is to conduct a comprehensive analysis of housing prices in New York City, identifying key factors that drive property valuations. Our goal is to develop predictive models capable of forecasting housing prices and generating actionable insights into the dynamics of the New York City housing market.

**Goals:**  
1. **Identify Key Factors:** Determine the primary factors affecting housing prices (beds, bath, property sqft, borough, property category,	type).
2. **Price Prediction:** Build regression models to predict housing prices based on features.
3. **Classify Housing Types:** Develop a classification model to categorize properties based on pricing categories.

---

## Meet the Team Members

- **Avineet Sharma**   
- **Marwa Bensalem** 
- **Natasha Anghelescu** 
- **Ryan Goldstein** 

---

## Data Gathering Approach

### **Kaggle Housing Dataset**
- **Source:** The primary dataset was obtained from Kaggle, which contains information on NYC housing prices, including features like property size, number of rooms, neighborhood, and price.
- **Key Features:** Property size, number of bedrooms, bathrooms, location (borough and neighborhood), amenities (e.g., parking, gym).

### **Reverse Geolocation API**
- **Purpose:** We used a reverse geolocation API to enrich the dataset with borough and neighborhood information based on geographic coordinates (latitude/longitude).
- **Rationale:** This allowed us to group properties by specific geographic areas and perform better spatial analysis on price trends.

---

## Data Exploration

- **Descriptive Statistics:** We calculated the mean, median, and standard deviation for key features (e.g., price, square footage).
- **Visualizations:**
  - **Price Distribution:** Histogram to visualize the distribution of housing prices across NYC.
  - **Price vs. Features:** Scatter plots to explore relationships between price and features like square footage and number of bedrooms.
  - **Correlation Matrix:** A heatmap to examine correlations between numeric variables and identify highly influential features.

---

## Data Cleanup

### **Missing Data**
- Imputation was used to handle missing values in non-essential columns (e.g., missing amenities information).
- Properties with significant missing data were removed.

### **Outliers**
- We identified and handled outliers using z-scores and IQR methods, adjusting or removing extreme outliers where necessary to ensure model accuracy.

### **Feature Engineering**
- Created new features such as price per square foot and neighborhood categories.
- One-hot encoding was applied to categorical features like neighborhood and property type.

---

## Regression Model and Results

### **Approach:**
- **Model:** We built a **Linear Regression** model to predict housing prices based on numeric features such as square footage, number of bedrooms,bathrooms and neighborhood.
- **Evaluation Metrics:** We used **Mean Squared Error (RMSE)**, and **R-squared** to evaluate model performance.

- Linear Regression         - MSE: 20109636019.6248, R2: 0.905373
- Decision Tree             - MSE: 3143092659.1132, R2: 0.985210
- Random Forest             - MSE: 574204422.6805, R2: 0.997298
- Gradient Boosting         - MSE: 600651851.4550, R2: 0.997174
- Support Vector Regressor  - MSE: 206634421425.1758, R2: 0.027673
  

### **Plot MSE results**
  
![image](https://github.com/user-attachments/assets/cab768cf-a573-4527-835a-f218b48b7fe7)




### **Plot R2 results**

![image](https://github.com/user-attachments/assets/b48181b0-9b55-48f8-bc03-e2519f0d8fa7)




### **Results:**
- **R-squared:** Indicating that depending on the model, 90-99%  of the variance in housing prices was explained by the model.
- **Key Predictors:** Location (borough), property size (square footage), and the number of bedrooms were the most influential factors.
- **Model Insights:** The model suggests that proximity to Manhattan and certain high-demand neighborhoods (e.g., Brooklyn) significantly increase property prices.
- Based on the evaluation, the best model is: **Random Forest with highest R2 score, 0.9972**

![image](https://github.com/user-attachments/assets/f860a37c-216c-46b0-95b8-2d75cfebb126)


---

## Classification Model and Results

### **Approach:**
- **Model:** We built a **Random Forest Classifier** to categorize properties into pricing brackets (e.g., Low, Medium, High) based on key features.
- **Evaluation Metrics:** We used **Accuracy**, **Precision**, **Recall**, and **F1 Score** for model evaluation.

### **Results:**
- **Accuracy:** 0.78 – meaning 78% of the time, the model correctly predicted the price category.
- **Precision and Recall:** High precision for the "High Price" category, indicating good detection of luxury properties.
- **Model Insights:** The classification model revealed that properties with specific amenities (e.g., parking, gyms) and those in certain high-demand neighborhoods were most likely to fall into the "High Price" category.

---

## Next Steps

1. **Improve Model Performance:**
   - **Additional Data:** This will enhance the model's ability to capture complex relationships and provide more accurate predictions, as a broader dataset can improve its generalizability and robustness.
   - **More Features:** One example of such a feature could be proximity to city center. This can also be accomplished through further data collection.
