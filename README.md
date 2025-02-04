## Table of Contents
1. [Measures of Central Tendency](#measures-of-central-tendency)
2. [Measures of Spread](#measures-of-spread)
3. [Understanding Skewness and Kurtosis](#understanding-skewness-and-kurtosis)
4. [Percentile and Quartiles](#percentile-and-quartiles)
5. [Box Plots & Histograms](#box-plots-and-histograms)
6. [Probability Rules](#probability-rules)


## **Measures of Central Tendency**

### **Mean (Average)**  
The **mean** (also called the **average**) is the **sum of all values divided by the number of values**. It is one of the most widely used measures of central tendency.


#### **Why Is the Mean Important?**
1. ***Represents the Overall Trend*** 📈  
   - The mean gives a **single value** that summarizes the entire dataset.  
   - Example: **Exam Scores**  
     - Scores: `[75, 80, 85, 90, 95]`  
     - Mean = (75 + 80 + 85 + 90 + 95) / 5 = **85**  
     - The class's overall performance is around 85.  

2. ***Best for Symmetrical Data (Normal Distributions)*** 🛠️  
   - When data is **evenly spread**, the mean is the most **accurate measure of center**.  
   - Example: **Heights of a Population**  
     - If heights follow a **bell curve**, the mean gives a reliable "typical" value.  

3. ***Useful for Continuous Data*** 🔢  
   - Works well for **measurements like weight, height, temperature, or revenue**.  
   - Example: **Company Revenue**  
     - A company calculates its **average monthly revenue** to track financial health.  

4. ***Key for Many Statistical Methods*** 🧠  
   - Used in **machine learning, finance, economics, and data analysis**.  
   - **Variance and standard deviation** are calculated using the mean.
---



### **Median**  
The **median** is the middle value of a dataset when arranged in ascending order. It is especially useful in cases where the **mean (average) is misleading due to outliers or skewed data**.  


#### **Why Is the Median Important?**
1. ***Resistant to Outliers*** 🚀  
   - Example: **House Prices**  
     - Dataset: `[300K, 320K, 350K, 2M]`  
     - **Mean:** ~742K (skewed by 2M house)  
     - **Median:** 335K (better represents the typical home price)  

2. ***Better for Skewed Data*** 📈📉  
   - Example: **Income Distribution**  
     - A few billionaires in a dataset will pull the **mean** up, but the **median** remains stable.  
     - Governments often use **median income** instead of **average income** for fair comparisons.  

3. ***Useful for Non-Normal Distributions*** 🛠️  
   - In datasets with **long tails** or **asymmetrical shapes**, the **median** gives a more accurate center.  

4. ***Ideal for Ordinal Data (Ranks, Ratings, Surveys)***  
   - Example: **Customer Ratings (1-5 Stars)**  
     - If reviews are `[1, 2, 2, 4, 5, 5, 5]`, the median (4) makes more sense than the mean (~3.43).  

---  


### **Mode**  
The **mode** is the value that appears most frequently in a dataset. Unlike the **mean** and **median**, the mode is particularly useful for **categorical** or **discrete data** where the most common occurrence matters.


#### **Why Is the Mode Important?**  

1. ***Best for Categorical Data*** 🏷️  
   - The **mean and median don’t work for non-numeric data**, but the mode does.  
   - **Example: Favorite Fruits Survey**  
     - Data: `["Apple", "Banana", "Apple", "Orange", "Apple"]`  
     - Mode: **"Apple"** (most chosen fruit).  

2. ***Identifies the Most Common Value*** 🔍  
   - Example: **Shoe Sizes in a Store**  
     - Sizes: `[7, 8, 9, 9, 9, 10, 10, 11]`  
     - Mode: **9** (most common size, so the store stocks more of it).  

3. ***Works Well for Discrete & Count Data*** 🔢  
   - Example: **Number of Children per Family**  
     - Families have `[2, 3, 2, 4, 2, 1, 3]` children.  
     - Mode: **2** (most families have **2 children**).  

4. ***Helps in Detecting Trends & Peaks*** 📈  
   - In large datasets, multiple peaks (modes) indicate trends.  
   - **Example: Sales Demand**  
     - If a company sees mode = **"laptop"**, it’s the best-selling product.  

#### **Limitations of the Mode**
1. ***May Not Exist or Be Unique*** ❓  
   - Example: `[1, 2, 3, 4, 5]` → No mode (all values appear once).  
   - Example: `[1, 2, 2, 3, 3, 4]` → Two modes (Bimodal Distribution).  

2. ***Less Useful for Continuous Data*** 📉  
   - For **decimal-based measurements (e.g., height, weight, income),** mode often lacks meaning.  

---

### **Comparison: Mode vs. Mean vs. Median**
| Feature  | Mode | Mean | Median |
|----------|------|------|--------|
| Works for Categorical Data? | ✅ Yes | ❌ No | ❌ No |
| Works for Numerical Data? | ✅ Yes | ✅ Yes | ✅ Yes |
| Affected by Outliers? | ❌ No | ✅ Yes | ❌ No |
| Useful for Skewed Data? | ✅ Yes | ❌ No | ✅ Yes |


[🔼 Back to Top](#table-of-contents)

## **Measures of Spread**

**Measures of spread** tell us **how dispersed or spread out** the data is. They help us understand how much **variability** exists in a dataset.  

The four key measures of spread are:  
1. **Range** 📏  
2. **Interquartile Range (IQR)** 📊  
3. **Variance** 📈  
4. **Standard Deviation** 📉  

---

### **1️⃣ Range: The Simplest Measure of Spread**
- **Definition:** The difference between the **maximum** and **minimum** values in a dataset.  
- **Formula:**  
  $$\text{Range} = \text{Max Value} - \text{Min Value}$$
- **Example:**  
  - Data: `[10, 20, 30, 40, 50]`  
  - Range = **50 - 10 = 40**  
- **Limitation:**  
  - **Sensitive to outliers** (a single extreme value can distort the range).

#### **Real-World Example: Temperature Variations 🌡️**  
- Suppose you check the temperature in San Francisco over a week:  
  - **Temperatures**: `[50°F, 52°F, 55°F, 60°F, 62°F, 64°F, 66°F]`  
  - **Range** = `66°F - 50°F = 16°F`  
- **Interpretation:**  
  - SF has a **small range**, meaning the temperature is fairly stable.  
  - In contrast, a desert might have a range of **40°F to 100°F** (range = 60°F), showing huge daily fluctuations.  

📌 **Use Case:** **Weather forecasting**, stock price analysis, sports performance comparisons.  


---

### **2️⃣ Interquartile Range (IQR): Spread of the Middle 50%**
- **Definition:** The range of the **middle 50% of data** (between Q1 and Q3).  
- **Formula:**  
  $$\text{IQR} = Q3 - Q1$$
  - **Q1 (25th percentile):** The middle value of the first half.  
  - **Q3 (75th percentile):** The middle value of the second half.  
- **Example:**  
  - Data: `[5, 10, 15, 20, 25, 30, 35]`  
  - **Q1 = 10**, **Q3 = 30**  
  - **IQR = 30 - 10 = 20**  
- **Why Use IQR?**  
  - **Not affected by outliers**, unlike range.  
  - Used in **box plots** to detect **outliers**.

#### **Real-World Example: Income Distribution 💰**  
- Suppose we analyze **monthly salaries** in a company:  
  - **Salaries**: `[3K, 3.5K, 4K, 4.5K, 5K, 50K]`  
  - **Q1 = 3.5K**, **Q3 = 5K**  
  - **IQR = 5K - 3.5K = 1.5K**  
- **Why is IQR Useful?**  
  - The **50K outlier** (CEO’s salary) **won’t impact the IQR**.  
  - It shows that most employees earn between **3.5K and 5K**, even if one person earns 50K.  

📌 **Use Case:** **Income analysis, student test scores, housing prices.**  


---

### **3️⃣ Variance: The Average Squared Deviation from the Mean**
- **Definition:** Measures how far each value in the dataset is from the mean.  
- **Formula:**  
  $$\text{Variance} (\sigma^2) = \frac{\sum (x_i - \bar{x})^2}{n}$$
  - $$\( x_i \)$$ = Each data point  
  - $$\( \bar{x} \)$$ = Mean of the data  
  - $$\( n \)$$ = Number of data points  

- **Example:**  
  - Data: `[10, 20, 30]`  
  - Mean = **(10+20+30)/3 = 20**  
  - Variance = **[(10-20)² + (20-20)² + (30-20)²] / 3**  
  - = **[(100 + 0 + 100) / 3] = 66.67**  

- **Interpretation:**  
  - **Low variance** → Data points are close to the mean (less spread).  
  - **High variance** → Data points are far from the mean (more spread).

#### **Real-World Example: Manufacturing Quality Control 🏭**  
- Suppose a factory produces **water bottles**, and we measure their weights:  
  - **Bottle Weights (grams):** `[500, 502, 498, 505, 495, 550]`  
  - **Mean Weight = ~508g**  
  - **Variance = High** because one bottle weighs **550g**, far from the others.  

- **Interpretation:**  
  - **Low variance** → Most bottles weigh around 500g, meaning **consistent quality**.  
  - **High variance** → Some bottles are much heavier/lighter, meaning **poor quality control**.  

📌 **Use Case:** **Manufacturing, stock market fluctuations, machine learning feature importance.** 

---

### **4️⃣ Standard Deviation: The Square Root of Variance**
- **Definition:** Measures the **average distance** of each data point from the mean.  
- **Formula:**  
  $$\text{Standard Deviation} (\sigma) = \sqrt{\text{Variance}}$$
- **Example (from previous variance calculation):**  
  - Variance = **66.67**  
  - Standard Deviation = **√66.67 = 8.16**  

- **Why Use Standard Deviation Instead of Variance?**  
  - The **variance is squared**, making it hard to interpret.  
  - Standard deviation is in the **same units** as the data, making it easier to understand.

#### **Real-World Example: Exam Performance in a Class 📚**  
- Suppose two classes take a **math test**, and we analyze their scores:  

| Class | Scores | Mean | Standard Deviation |
|-------|--------|------|-------------------|
| **Class A** | `[80, 82, 85, 88, 90]` | **85** | **4** (low variability) |
| **Class B** | `[50, 60, 70, 90, 100]` | **74** | **18** (high variability) |

- **Interpretation:**  
  - **Class A** has a **small standard deviation**, meaning most students scored close to **85**.  
  - **Class B** has a **high standard deviation**, meaning some students did very well, while others struggled.  

📌 **Use Case:** **Education performance, sports analytics, financial risk assessment.**  


---

### **Comparing the Measures of Spread**
| Measure | Formula | Best For | Affected by Outliers? |
|---------|--------|----------|---------------------|
| **Range** | Max - Min | Quick estimation of spread | ✅ Yes |
| **IQR** | Q3 - Q1 | Skewed distributions, box plots | ❌ No |
| **Variance** | Avg. squared difference from mean | Overall spread, statistics & ML | ✅ Yes |
| **Standard Deviation** | √Variance | Understanding data variability | ✅ Yes |

---

### **Python Code to Visualize These Measures** 📊
```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Sample dataset
data = [10, 20, 30, 40, 50, 60, 70, 80, 100]

# Calculate measures
range_value = max(data) - min(data)
q1, q3 = np.percentile(data, [25, 75])
iqr = q3 - q1
variance = np.var(data)
std_dev = np.std(data)

# Print results
print(f"Range: {range_value}")
print(f"IQR: {iqr}")
print(f"Variance: {variance}")
print(f"Standard Deviation: {std_dev}")

# Boxplot to visualize spread
plt.figure(figsize=(8, 5))
sns.boxplot(data=data)
plt.title("Boxplot Showing Spread (IQR, Outliers)")
plt.show()
```
Range: 90
IQR: 40.0
Variance: 765.4320987654321
Standard Deviation: 27.666443551086072
![image](https://github.com/user-attachments/assets/f0a46066-f86c-46b4-905e-8d6538720a47)

---

### **Summary of When to Use Each Measure**
- Use **Range** when you need a **quick estimate** of spread.  
- Use **IQR** when you want a **robust** measure that ignores outliers.  
- Use **Variance** when working with **machine learning** and statistical models.  
- Use **Standard Deviation** for a **simple, interpretable measure of spread**.


### **Summary Table of Real-World Applications**  

| Measure | Real-World Example | Why It Matters |
|---------|--------------------|----------------|
| **Range** | Temperature variations | Quick estimate of fluctuation |
| **IQR** | Income distribution | Ignores extreme outliers |
| **Variance** | Factory product quality | Identifies inconsistencies |
| **Standard Deviation** | Exam scores, stock prices | Measures typical variation |

---

### **Final Thought:**  
👉 **When data has extreme values (outliers), use IQR instead of Range.**  
👉 **When precision is needed, Standard Deviation is better than Range.**  
👉 **Variance is useful for calculations but hard to interpret directly.**  


[🔼 Back to Top](#table-of-contents)


---

## **Understanding Skewness and Kurtosis**

Skewness and kurtosis are key statistical concepts used to understand the **shape** of a probability distribution beyond just the mean and variance.  


### **1️⃣ Skewness (Measure of Symmetry)**
Skewness tells us **how symmetric or asymmetric** a distribution is.  

- **Zero Skewness (Symmetric Distribution)**
  - The left and right sides of the distribution are **evenly balanced**.
  - Example: **Human heights**.

- **Positive Skewness (Right-Skewed)**
  - The **right tail is longer** (more extreme high values).
  - Mean > Median > Mode.
  - Example: **Income distribution (most earn average, a few earn very high salaries)**.

- **Negative Skewness (Left-Skewed)**
  - The **left tail is longer** (more extreme low values).
  - Mode > Median > Mean.
  - Example: **Time taken to complete an easy exam (most finish quickly, few take long)**.

---

### **2️⃣ Kurtosis (Measure of Tailedness)**
Kurtosis tells us **how extreme values behave** in a distribution.  

- **Normal Kurtosis (Mesokurtic, ≈3)**
  - Standard bell curve.
  - Moderate frequency of extreme values.
  - Example: **Human heights**.

- **High Kurtosis (Leptokurtic, >3)**
  - **Fat tails** = More frequent extreme values (outliers).
  - The peak is often sharper.
  - Example: **Stock market crashes (rare but extreme events like 2008 crisis)**.

- **Low Kurtosis (Platykurtic, <3)**
  - **Thin tails** = Fewer extreme values, more uniform shape.
  - The peak is flatter.
  - Example: **Easy exam scores (most students score within a narrow range)**.

---

### **Does High Kurtosis Mean Higher Probability of Extreme Values?**
✅ **Yes!** High kurtosis distributions have **more extreme values** than normal distributions.  
✅ This does **not necessarily** mean higher overall variance, but **outliers occur more often**.  
🚀 **Example:** Stock returns—normal conditions are stable, but when a crash happens, it’s severe.

---

### **Visualization (Skewness & Kurtosis Combinations)**  

We have discussed **9 cases** based on skewness and kurtosis. Below are their characteristics:

| Skewness \ Kurtosis | **Normal Kurtosis** (≈3) | **High Kurtosis** (>3) | **Low Kurtosis** (<3) |
|---------------------|------------------------|----------------------|----------------------|
| **Zero Skew** (Symmetric) | Standard Bell Curve (Heights) | More Outliers (Stock Market Crashes) | Flat Distribution (Uniform Exam Scores) |
| **Positive Skew** (Right) | Salaries (Few High Earners) | More Extreme High Salaries (Startup IPOs) | Capped Salaries (Fixed Pay Bands) |
| **Negative Skew** (Left) | Exam Completion Time | Rare but Extreme Delays (Flights) | Discounted Prices (Narrow Range) |

![image](https://github.com/user-attachments/assets/4f709ede-1bd5-4678-ab77-7d1f4fa552aa)


[🔼 Back to Top](#table-of-contents)

---

## **Percentile and Quartiles**
Percentiles and quartiles are both ways of dividing data into groups, helping to understand the distribution of a dataset. Here's an overview:

### Percentiles
- **Definition:** A percentile is a value below which a given percentage of observations in a dataset fall. 
- **Percentile Notation:** If you're looking at the *p*-th percentile, it means the value below which *p* percent of the data points lie.
  - **For example**: The 50th percentile (often called the median) is the value where half of the data is less than this value, and half is greater.
- **Key Percentiles:**
  - **25th percentile (P25)**: 25% of the data is below this value.
  - **50th percentile (P50)**: Also known as the median, 50% of the data is below this value.
  - **75th percentile (P75)**: 75% of the data is below this value.
- **How to Calculate:** Sort your data in ascending order and find the value at the desired percentile. There are formulas and interpolation methods to handle cases when the percentile doesn't exactly match a data point.

### Quartiles
- **Definition:** Quartiles divide data into four equal parts. There are three quartiles:
  - **First Quartile (Q1)**: The 25th percentile; 25% of the data points lie below Q1.
  - **Second Quartile (Q2)**: The 50th percentile; it is the median.
  - **Third Quartile (Q3)**: The 75th percentile; 75% of the data points lie below Q3.
- **Interquartile Range (IQR):** This is the range between Q1 and Q3 (Q3 - Q1) and represents the spread of the middle 50% of the data.
  - **IQR = Q3 - Q1**

### Example:
Consider this dataset:  
**3, 7, 8, 12, 15, 18, 20, 25, 30**

1. **Arrange the data**: It's already sorted.
2. **Median (Q2)**: The middle value is 15, so the median (Q2) is 15.
3. **First Quartile (Q1)**: The median of the lower half (3, 7, 8, 12) is 7.5, so Q1 = 7.5.
4. **Third Quartile (Q3)**: The median of the upper half (18, 20, 25, 30) is 22.5, so Q3 = 22.5.
5. **Interquartile Range (IQR)**:  
   \( IQR = Q3 - Q1 = 22.5 - 7.5 = 15 \)

This provides a clearer picture of how the data is spread and where the majority of the values fall.

[🔼 Back to Top](#table-of-contents)

---

## **Box Plots and Histograms**  

Both **box plots** and **histograms** help visualize data distribution, but they serve different purposes. Let’s break them down.


### **1. Box Plot (Box-and-Whisker Plot)**
A **box plot** is a graphical summary of data that displays the **median, quartiles, and outliers**. It helps quickly identify **skewness, spread, and potential outliers**.

#### **Components of a Box Plot**  
1. **Minimum (Lower Whisker)**: The smallest value within 1.5×IQR from Q1.  
2. **First Quartile (Q1, 25th percentile)**: The median of the lower half of the dataset.  
3. **Median (Q2, 50th percentile)**: The middle value of the dataset.  
4. **Third Quartile (Q3, 75th percentile)**: The median of the upper half of the dataset.  
5. **Maximum (Upper Whisker)**: The largest value within 1.5×IQR from Q3.  
6. **Outliers**: Any data points beyond 1.5×IQR are marked separately (dots or stars).

#### **Interquartile Range (IQR)**
$$IQR = Q3 - Q1$$
- **Lower fence**: $$\( Q1 - 1.5 \times IQR \)$$  
- **Upper fence**: $$\( Q3 + 1.5 \times IQR \)$$  
- Any values beyond this range are **outliers**.

#### **Example Box Plot**

![image](https://github.com/user-attachments/assets/e5e84f8d-dc04-4ec4-a81e-a700934b5140)

If data is **right-skewed**, the median is closer to Q1. If **left-skewed**, it’s closer to Q3.

---

### **2. Histogram**
A **histogram** is a bar chart that represents the **frequency distribution** of a dataset by grouping data into **bins (intervals).**  
It shows how often each range of values appears.

#### **Key Features**
- **X-axis (Bins/Intervals)**: Divides the data into ranges.
- **Y-axis (Frequency)**: The number of values in each bin.
- **Shape of Distribution**:
  - **Bell-shaped (Normal Distribution)**
  - **Right-skewed (Positive Skew)**
  - **Left-skewed (Negative Skew)**
  - **Uniform (Flat)**
  - **Bimodal (Two Peaks)**

---

### **Comparison: Box Plot vs Histogram**
| Feature | Box Plot | Histogram |
|---------|---------|------------|
| **Shows** | Median, quartiles, outliers | Frequency of data |
| **Best for** | Identifying outliers, skewness, and spread | Understanding overall shape of distribution |
| **Handles Outliers** | Explicitly marks them | Can be hard to spot |
| **Data Required** | Summary statistics | Full dataset |

---

### **Which One Should You Use?**
- Use **box plots** to compare multiple datasets and detect outliers.
- Use **histograms** to understand the overall distribution shape and frequency.

---

### **Justification: "1.5×IQR Covers Most of the Normal Data Spread"**  

The **1.5×IQR rule** is widely used to identify **moderate outliers** in a dataset. This choice is based on **statistical reasoning** and works well for **many real-world distributions, especially normal distributions**.

---

### **1. Relationship Between IQR and Standard Deviation (σ)**
For a **normal distribution**, the interquartile range (IQR) and standard deviation (σ) are related:

$$IQR \approx 1.35 \times \sigma$$

Since the **1.5×IQR rule** defines outliers, let's express it in terms of **σ**:

$$1.5 \times IQR \approx 1.5 \times (1.35 \times \sigma) = 2.025 \times \sigma$$

This means the **lower and upper fences (Q1 - 1.5×IQR and Q3 + 1.5×IQR)** correspond roughly to **±2.025 standard deviations (σ) from the median** in a normal distribution.

---

### **2. Coverage in a Normal Distribution**
In a **normal distribution**, we know that:
- **68%** of data falls within **±1σ**.
- **95%** of data falls within **±2σ**.
- **99.7%** of data falls within **±3σ**.

Since the **1.5×IQR range corresponds to approximately ±2.025σ**, it **captures roughly 95% of the data in a normal distribution**.  
Thus, **only about 5% of values (2.5% on each tail) fall outside this range**, making them potential outliers.

---

### **3. Why 1.5 Instead of 2 or 3?**
- **1.5×IQR is strict enough to flag unusual points** but **not too extreme** that it falsely labels common values as outliers.
- **2×IQR or 3×IQR** would detect **fewer** outliers, possibly missing moderate deviations.
- **1.0×IQR** would be too sensitive, flagging many normal points as outliers.

---

### **4. Practical Example**
Consider a **normally distributed dataset** with mean = 50 and σ = 10.  
- **IQR ≈ 1.35 × 10 = 13.5**
- **Lower Fence ≈ Q1 - 1.5×13.5**
- **Upper Fence ≈ Q3 + 1.5×13.5**

Most data (95%) stays within this range, while **extreme values (beyond ±2σ) are flagged as outliers**.

---

### **5. Works Well for Other Distributions**
While the **1.5×IQR rule** is based on the normal distribution, it **also works well for skewed and non-normal distributions**, making it a **robust choice** for general outlier detection.

---

### **Conclusion**
✔ **1.5×IQR covers approximately 95% of a normal distribution’s data**.  
✔ **It helps detect moderate outliers while avoiding excessive false positives**.  
✔ **It is simple, robust, and widely used in statistics, data science, and machine learning**.

[🔼 Back to Top](#table-of-contents)

---

## **Probability Rules**
Let's **dive deep** into **Probability Rules**—Addition, Multiplication, and Complement—with explanations, formulas, and examples.

### **What is Probability?**
Probability measures the **likelihood** of an event occurring and is always between **0 and 1**:
$$0 \leq P(A) \leq 1$$
- **P(A) = 0** → The event **never happens** (impossible event).  
- **P(A) = 1** → The event **always happens** (certain event).  
- **P(A) = 0.5** → The event has a **50% chance** of happening.  

### **Basic Definitions**
- **Sample Space (S)**: The set of all possible outcomes.  
  - Example: For a **die roll**, $$\( S = \{1,2,3,4,5,6\} \)$$.  
- **Event (A)**: A subset of the sample space.  
  - Example: $$\( A = \{\text{rolling an even number}\} = \{2,4,6\} \)$$.  

---
  
### **2. Addition Rule (For Union of Events)**
#### **Case 1: Mutually Exclusive Events**
Events **A and B** are **mutually exclusive** if **they cannot happen at the same time** (no overlap).

$$P(A \cup B) = P(A) + P(B)$$

🔹 **Example**: Rolling a **die**, probability of rolling a **3 or a 5**:  

$$P(3) + P(5) = \frac{1}{6} + \frac{1}{6} = \frac{2}{6} = \frac{1}{3}$$
  
#### **Case 2: Non-Mutually Exclusive Events**
If events **can overlap**, we must **subtract the double-counted part**:

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

🔹 **Example**: In a school of **100 students**:
- **50 take Math** → $$\( P(M) = \frac{50}{100} = 0.5 \)$$  
- **40 take Science** → $$\( P(S) = \frac{40}{100} = 0.4 \)$$  
- **20 take both Math and Science** → $$\( P(M \cap S) = \frac{20}{100} = 0.2 \)$$  

Applying the formula:
$$P(M \cup S) = P(M) + P(S) - P(M \cap S)$$ $$= 0.5 + 0.4 - 0.2 = 0.7$$

##### **Interpretation**
- The probability that a randomly selected student is **taking Math or Science** is **0.7 (70%)**.
- If we had **not subtracted** $$\( P(M \cap S) \)$$, we would have **double-counted the 20 students** taking both subjects.

---
  
### **3. Multiplication Rule (For Intersection of Events)**
#### **Case 1: Independent Events**
Events **A and B are independent** if one **does not affect** the probability of the other:

$$P(A \cap B) = P(A) \times P(B)$$

🔹 **Example**: Flipping two fair coins, probability of getting **two heads**:

$$P(H) \times P(H) = \frac{1}{2} \times \frac{1}{2} = \frac{1}{4}$$

#### **Case 2: Dependent Events**
Events are **dependent** if one event **affects** the probability of another:

$$P(A \cap B) = P(A) \times P(B | A)$$

🔹 **Example**: Drawing **two aces in a row** from a deck of 52 cards **without replacement**: 

- $$\( P(A_1) = \frac{4}{52} \)$$ (First ace)
- $$\( P(A_2 | A_1) = \frac{3}{51} \)$$ (Second ace after first is removed)
  
$$P(A_1 \cap A_2) = \frac{4}{52} \times \frac{3}{51} = \frac{12}{2652} \approx 0.0045$$

---
  
### **4. Complement Rule (For "Not" Events)**
The probability of an event **not occurring**:

$$P(A^c) = 1 - P(A)$$

🔹 **Example**: If the probability of rain today is **0.3**, then:  

$$P(\text{No Rain}) = 1 - 0.3 = 0.7$$

---
  
### **5. Summary**
| Rule | Formula | Example |
|------|---------|---------|
| **Addition (Mutually Exclusive)** | $$\( P(A \cup B) = P(A) + P(B) \)$$ | Rolling a **3 or 5** on a die |
| **Addition (Non-Mutually Exclusive)** | $$\( P(A \cup B) = P(A) + P(B) - P(A \cap B) \)$$ | Drawing a **red or face card** |
| **Multiplication (Independent Events)** | $$\( P(A \cap B) = P(A) \times P(B) \)$$ | Flipping **two heads** in a row |
| **Multiplication (Dependent Events)** | $$\( P(A \cap B) = P(A) \times P(B | A) \)$$ | Drawing **two aces in a row** |
| **Complement Rule** | $$\( P(A^c) = 1 - P(A) \)$$ | Probability of **no rain** |

---

[🔼 Back to Top](#table-of-contents)




