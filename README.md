# Event Watch Time – Data Analysis & Visualization

An exploratory data analysis project focused on cleaning, preprocessing, analyzing, and visualizing a large dataset in order to understand the factors associated with event watch time.

The project works with **750,000 observations and 12 variables** and explores both numerical and categorical features.

## Dataset

The dataset is adapted from the **Kaggle Playground Series – Season 5, Episode 4: Predict Podcast Listening Time** competition.

For this course project, some column names were adapted to use event-related terminology.

The dataset itself is not included in this repository. The notebook expects the original training data to be loaded before running the analysis.

## Project Workflow

The analysis includes:

### 1. Initial Data Exploration

- Examining dataset dimensions and variable types
- Generating descriptive statistics
- Separating numerical and categorical variables
- Exploring category frequencies and numerical distributions

### 2. Missing Values

Missing values were identified in:

- `Event_Length_minutes`
- `Guest_Popularity_percentage`
- `Number_of_Sponsers`

Missing numerical values were replaced using the **median**, which is less sensitive to extreme values than the mean.

### 3. Outlier Detection and Treatment

Potential outliers were identified using the **Interquartile Range (IQR)** method.

Extreme values were handled using a capping approach based on the lower and upper IQR boundaries.

### 4. Feature Scaling

Numerical variables, excluding the identifier column, were normalized to the **0–1 range** using Min-Max scaling.

This allows variables measured on different scales to be compared more consistently.

### 5. Correlation Analysis

A correlation matrix was used to investigate relationships between numerical variables, with particular attention to `Watch_Time_minutes`.

The strongest observed relationship was between:

- **Event Length and Watch Time:** approximately **0.87** positive correlation

Other relationships with watch time were considerably weaker:

- Host Popularity: approximately **0.05**
- Guest Popularity: approximately **-0.01**
- Number of Sponsors: approximately **-0.12**

This suggests that event length is the numerical variable most strongly associated with watch time in the dataset.

## Data Visualization

Several visualization techniques were used throughout the analysis:

- Histograms
- Density plots
- Bar charts
- Correlation heatmap
- Scatter plots
- Boxplots

The visualizations were used to examine distributions, detect unusual observations, compare categories, and explore relationships with watch time.

Categorical comparisons included:

- Genre
- Event day
- Publication time
- Event sentiment

## Key Findings

- The average event length before normalization was approximately **64.5 minutes**.
- Average watch time was approximately **45.4 minutes**.
- Missing data appeared mainly in event length and guest popularity.
- Event length showed a strong positive relationship with watch time.
- Other numerical variables showed much weaker linear relationships with watch time.
- Data cleaning, outlier treatment, and normalization prepared the dataset for consistent exploratory analysis.

## Technologies Used

- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## File

`event_watch_time_analysis.ipynb` – complete exploratory data analysis, preprocessing, statistical summaries, and visualizations.

## Note

This project was completed as a group assignment.
