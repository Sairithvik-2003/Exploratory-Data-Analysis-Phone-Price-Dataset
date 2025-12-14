# 📱 Phone Price Feature Analysis & Exploratory Data Analysis (EDA)

This project performs **data cleaning, feature extraction, and exploratory data analysis (EDA)** on a smartphone pricing dataset to understand **which features truly influence phone prices**.

The problem statement for this project was inspired by an EDA practice challenge from:  
📎 https://datapecharcha.substack.com/p/kaggle-datasets-to-practice-eda-on

In addition to solving the given questions, this project includes **extra exploratory and comparative analysis** to uncover deeper insights.

---

## 📌 Problem Statement

This dataset helps answer:

> **Why is a phone priced the way it is?**

It is ideal for practicing **feature analysis, correlation analysis, and EDA**, helping uncover both expected and surprising relationships between phone specifications and price.

### Key Questions Explored
- How strong is the relationship between **RAM** and price?
- Do higher **camera megapixels** lead to higher prices?
- Do phones with higher **battery capacity** cost more?
- Does **screen size or resolution** impact pricing?
- Is **internal storage** as influential as RAM?

---

## 📂 Dataset Overview

### Raw Dataset Characteristics
- Smartphone specifications collected from online listings
- All columns initially stored as text (`object`)
- Inconsistent formats and noisy symbols (`?`, mixed units)
- Multiple features embedded inside single columns

### Raw Columns
- Name
- Price
- Memory
- Battery
- Display
- Camera

---

## 🧹 Step-by-Step Data Cleaning & Feature Engineering

### Step 1: Initial Data Inspection
- Checked first few rows, data types, and missing values
- Identified:
  - All columns as strings
  - Presence of `?` symbols
  - An unnecessary column (`Unnamed: 0`)

---

### Step 2: Dropping Irrelevant Column
- Removed `Unnamed: 0` since it contained no analytical value

---

### Step 3: Cleaning Price Column
- Removed `?` and commas
- Converted `price` to integer format
- Ensured numerical consistency

---

### Step 4: Memory Parsing (RAM & Storage)
- Cleaned memory text
- Extracted:
  - `ram` (GB)
  - `storage` (GB)
- Dropped original memory column

---

### Step 5: Battery Feature Extraction
- Cleaned battery column
- Extracted numeric `battery_mah`
- Dropped raw battery column

---

### Step 6: Display Feature Extraction
- Extracted:
  - `screen_size_inch`
  - `resolution_width`
  - `resolution_height`
- Removed original display column

---

### Step 7: Camera Feature Extraction
- Extracted:
  - `rear_camera_mp`
  - `front_camera_mp`
- Filled missing camera values with `0`
- Dropped original camera column

---

### Step 8: Column Selection for EDA
Kept only features relevant for price analysis:
- Price
- RAM
- Storage
- Battery
- Screen size
- Resolution
- Camera specs

---

### Step 9: Final Data Quality Check
- Checked missing values
- Dropped rows with missing key features
- Reset index

---

### Step 10: Saving Cleaned Dataset
- Final cleaned dataset saved as `Phone_Price_Cleaned.csv`

---

## 📊 Exploratory Data Analysis (EDA)

EDA is performed **in the same order as the notebook**, starting from simple distributions and moving toward relationship analysis.

---

## 🔹 Univariate Analysis (Single Feature Exploration)

### Price Distribution
- Highly right-skewed
- Majority of phones priced below ₹30,000
- Long premium tail with flagships

### RAM Distribution
- 4GB and 6GB dominate the market
- 8GB+ mainly in premium devices

### Storage Distribution
- 128GB is the new baseline
- 256GB rising in mid-range
- 512GB+ limited to flagships

### Battery Capacity Distribution
- 5000 mAh is the standard
- Larger batteries common in budget phones

### Screen Size Distribution
- Most phones fall between 6.4″–6.8″
- Very little variation across price ranges

### Camera MP Distributions
- Wide spread in megapixels
- No clear premium boundary from MP alone

---

## 🔹 Multivariate Overview (Correlation Matrix)

### Correlation Heatmap
- Shows relationships between all numeric features
- Helps identify strong vs weak price drivers

**Key Observation:**
- Storage shows the strongest correlation with price
- Battery capacity shows a negative relationship

---

## 🔹 Bivariate Analysis: Feature vs Price

### RAM vs Price
- **Correlation: +0.51 (Moderate)**
- Higher RAM generally increases price, but not decisively

---

### Rear & Front Camera MP vs Price
- Rear MP: **+0.13 (Very Weak)**
- Front MP: **+0.21 (Weak)**

**Conclusion:**  
Megapixels are not reliable indicators of phone price.

---

### Battery Capacity vs Price
- **Correlation: –0.21 (Weak Negative)**

**Conclusion:**  
Higher battery capacity does **not** imply a higher price.

---

### Screen Size & Resolution vs Price
- Screen size: **Very weak correlation**
- Resolution height: **Moderate correlation**

**Conclusion:**  
Display quality matters more than screen size.

---

### Storage vs Price (Compared with RAM)
- Storage: **+0.75 (Strong)**
- RAM: **+0.51 (Moderate)**

**Conclusion:**  
Storage is a stronger price driver than RAM.

---

## 📈 Final Insights Summary

| Feature | Correlation | Impact on Price |
|------|------------|----------------|
| Storage | +0.75 | Strong |
| RAM | +0.51 | Moderate |
| Resolution Height | +0.47 | Moderate |
| Camera MP | < 0.25 | Weak |
| Screen Size | +0.15 | Very Weak |
| Battery | –0.21 | Negative |

---

## 🔑 Final Conclusion

- **Internal storage is the strongest predictor of phone price**
- RAM contributes, but less than storage
- Camera megapixels are largely marketing-driven
- Battery size and screen size are poor indicators of premium pricing
- Display resolution impacts price more than physical screen size

---

## 📁 Repository Structure

| File | Description |
|----|------------|
| `EDA-Phone_Price.ipynb` | Full notebook with cleaning & EDA |
| `Phone_Price.csv` | Raw dataset |
| `Phone_Price_Cleaned.csv` | Cleaned dataset |

---

## ▶️ How to Run the Project

### Run Using VS Code
1. Install Python (3.8+)
2. Install VS Code
3. Install extensions: Python, Jupyter
4. Open the project folder
5. Open `EDA-Phone_Price.ipynb`
6. Select Python kernel
7. Run all cells

### Run Using Google Colab
1. Open Google Colab
2. Upload the notebook and CSV
3. Run all cells

---

## 🛠️ Tools & Technologies
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook
- Google Colab
- VS Code

---

## ✅ Project Status
✔ Completed  
📊 Includes additional analysis beyond the original problem statement  
💬 Open to feedback and suggestions
