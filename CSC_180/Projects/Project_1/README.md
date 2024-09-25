# CSC 180-01 Intelligent Systems  
## Project_1: Predicting Business Ratings Based on Customer Reviews and Other Business Attributes  

### Problem Statement  
The goal of this project is to develop a predictive model that estimates the star ratings of businesses based on a dataset containing customer reviews, business locations (latitude and longitude), and review count. The model should learn from these features to accurately predict the star ratings of businesses.

### Data Source  
The data was sourced from the [Yelp Dataset](https://www.yelp.com/dataset), and I extracted 1,000,000 rows of data from the reviews and business attributes provided.

---

### Methodology  

#### 1. Data Gathering and Preprocessing  
- Extracted data from the JSON files, creating two pandas DataFrames (`review` and `business`) from 1,000,000 rows.
- Removed businesses with fewer than 20 reviews from the review table.
- Grouped reviews by `business_id`.
- Merged the review DataFrame with the business DataFrame using `business_id`, including relevant features like latitude, longitude, review count, stars, and business name.

#### 2. Feature Extraction and Transformation  
- Applied **TF-IDF vectorization** to extract features from the review texts.
- Converted the merged DataFrame into a NumPy array, including additional features such as latitude, longitude, and review count.
- Combined these features with the TF-IDF vectorized features.

#### 3. Data Splitting  
- Defined the features (X) and the target variable (y, which represents the star ratings).
- Split the dataset into training and testing sets.

#### 4. Model Building  
- Developed multiple models using different configurations of activation functions (`ReLU`, `Sigmoid`, `Tanh`) and optimizers (`Adam`, `SGD`).

#### 5. Evaluation and Visualization  
- Plotted graphs to visualize the performance of different models.
- Created a table to display business names, their actual ratings, and the predicted ratings from the model.

---

### Experimental Results and Analysis  

#### Model 1:  
- **Model Configuration**: Sequential architecture with four hidden layers, using the ReLU activation function and Adam optimizer.  
- **Performance**: Achieved an RMSE of approximately 0.4543.  
- **Evaluation**: Reasonable predictive accuracy with room for improvement.  

#### Model 2:  
- **Model Configuration**: Four hidden layers with Sigmoid activation and the SGD optimizer.  
- **Performance**: RMSE of approximately 0.8218.  
- **Evaluation**: Lower predictive accuracy; Sigmoid may not be optimal for this problem.  

#### Model 3:  
- **Model Configuration**: Three hidden layers, using Tanh activation and Adam optimizer.  
- **Performance**: RMSE of approximately 0.8323.  
- **Evaluation**: Higher deviation; Tanh may not be suitable for this dataset.

---

### Task Division and Project Reflection  

#### Task Division  
This project was completed individually, and I was responsible for all aspects, including data collection, preprocessing, feature engineering, model development, and evaluation.

#### Challenges Encountered  
- **Chart Creation**: A significant challenge was creating proper data visualizations for performance analysis.

#### Learning Outcomes  
- **Concatenating Arrays and DataFrames**: Practical experience in merging various data structures for model input.  
- **Experimenting with Activations and Optimizers**: Learned the effects of different activation functions and optimizers on model performance.  
- **Creating Charts**: Developed skills in visualizing data to communicate results effectively.  
- **Understanding Neuron Impact**: Gained insight into how the number of neurons affects the predictive capabilities of models.
