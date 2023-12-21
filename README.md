# Python: Identifying and Visualising All Nobel Prize Winners

### Project Overview
---

This data analysis project conducted via **Python** is intended to identify undiscovered patterns by exploring Nobel Prize winner data. 

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Python.-Identifying-and-Visualising-Nobel-Prize-Winners/blob/main/Nobel_Prize.png")
 alt="Alfred Nobel">
</p>


Awards are bestowed in chemistry, literature, physics, physiology or medicine, economics, and peace. 
Made available by the Nobel Foundation, the analysed data includes all prize winners from the beginning of all awards being granted from 1901 to 2023.


### Data Sources

The dataset used for this analysis is the *"nobel.csv"* file, containing detailed information about each award winner up to date ever since the Prize was established.

### Tools

- [Anaconda Navigator: ](https://www.anaconda.com/download)
  - To access the Jupyter Notebook


### Data Preparation

Only *the nobel.csv* dataset was first inspected and imported into a Pandas DataFrame to begin conducting the exploratory data analysis:


### Exploratory Data Analysis

EDA involved exploring the nobel prize data to answer key questions, such as:

1.  What has been the most commonly awarded gender and birth country up to date?
2.  What has been the proportion of US-born winners per decade?
3.  What has been the proportion of female laureates per decade and category?
4.  Who was the first woman to receive a Nobel Prize, and in what category?
5.  Which individuals and organisations have won the Prize for more than once?


### Data Analysis

The following code helped me consolidate my knowledge in subsetting, filtering and then grouping the resulting subset by two separate categories for a count-type aggregate operation:

```python
female_winners = nobel_winners_df[nobel_winners_df['sex'] == 'Female'].groupby(['decade',
                                                                                'category']).agg({"prize":"count"})
```

In addition, the code below helped me clear out the blurry lines between a Pandas Series and DataFrames where each one of those have a different set of functions and methods:

```python
top_birth_country = nobel_winners_df["birth_country"].value_counts().reset_index().iloc[0,0]
```

### Findings

The critical analysis results are summarised as follows:

1. The most commonly awarded gender and top birth country of the award winners respectively turn out to be **Male** and **the United States of America.**
2. The proportion of US-born award winners till 2000 was in a gradual uptrend, peaking at slightly higher than **the 0.4 ratio**, before dipping by nearly **25%** during 2000s.
3. Female award winners have almost entirely dominated the disciplines of **Peace and Literature** as of the 2000s.
4. **Marie Curie**, née Sklodowska was the first woman to receive a Nobel Prize in the category of **Physics**.


### Limitations


### References

1. [DataCamp](https://www.datacamp.com/)
2. [GeeksforGeeks: Use of Cut Function](https://www.geeksforgeeks.org/pandas-cut-method-in-python/)

