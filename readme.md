# Association Rule Mining for Market Basket Analysis

<div align="center">
<img height="300" width="700" src="https://media.licdn.com/dms/image/v2/C4E12AQGU1v7D_aF3Fg/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1520139318564?e=2147483647&v=beta&t=02RtjMYVUFydfQ2Ho4cfcbc5FRc27WLVawp9lBFGWdg">

</div>

## Project – Market Basket Analysis Using Association Rule Mining

### Introduction
In this Project, we implemented the **Apriori Algorithm** to perform **Market Basket Analysis**. The goal was to discover associations between items in a dataset of transactions (e.g., items frequently bought together in a store). The dataset used in this workshop was personalized for each student using a unique identifier.

---

## Methodology

### Data Preparation
1. **Generate Personalized Dataset**:
   - A subset of the original dataset was created using the following code:
     ```python
     np.random.seed(int(STUDENT_NO))
     unique_id = int('2' + STUDENT_NO)
     rows = np.random.choice(df.index.values, unique_id)
     data = df.loc[rows]
     ```
   - This generated a unique dataset with **21,202 rows**, stored in `MameFasseSALL_1202_6.csv`.

2. **Create Transaction Baskets**:
   - The dataset was transformed into a list of transactions (baskets), where each basket contains a list of items.

---

### Apriori Algorithm
The **Apriori Algorithm** was applied to find association rules between items. The algorithm was run with three different parameter settings:

1. **Setting 1**:
   - `min_support = 0.01`
   - `min_confidence = 0.2`
   - `min_lift = 3`
   - `min_length = 2`
   - **Result**: Generated **91 association rules**.

2. **Setting 2**:
   - `min_support = 0.015`
   - `min_confidence = 0.7`
   - `min_lift = 3`
   - `min_length = 2`
   - **Result**: Generated **4 association rules**.

3. **Setting 3**:
   - `min_support = 0.009`
   - `min_confidence = 0.5`
   - `min_lift = 3`
   - `min_length = 2`
   - **Result**: Generated **55 association rules**.

4. **Setting 4**:
   - `min_support = 0.015`
   - `min_confidence = 0.5`
   - `min_lift = 9`
   - `min_length = 2`
   - **Result**: Generated **12 association rules**.

---

### Results and Discussion

#### Association Rules
- **Higher Confidence**: Fewer rules were generated, but they were more reliable.
- **Lower Support**: More rules were generated, but they were less reliable.
- **Higher Lift**: Stronger associations were selected, ensuring the rules were meaningful.

#### Top 10 Most Common Items
The top 10 most common items in the dataset were:
1. WHITE HANGING HEART T-LIGHT HOLDER (1615)
2. REGENCY CAKESTAND 3 TIER (1519)
3. JUMBO BAG RED RETROSPOT (1455)
4. PARTY BUNTING (1155)
5. LUNCH BAG RED RETROSPOT (1061)
6. ASSORTED COLOUR BIRD ORNAMENT (964)
7. LUNCH BAG BLACK SKULL (922)
8. PACK OF 72 RETROSPOT CAKE CASES (921)
9. SET OF 3 CAKE TINS PANTRY DESIGN (915)
10. NATURAL SLATE HEART CHALKBOARD (856)

#### Comparison with Association Rules
- None of the top 10 items appeared in the association rules.
- **Reason**: These items are popular but do not form strong associations with other items. They may be bought alone or in diverse contexts, reducing their importance in association rules.

---

### Conclusion
- The Apriori Algorithm effectively identified meaningful association rules in the dataset.
- Parameter tuning (support, confidence, lift) significantly impacted the number and quality of rules generated.
- The top 10 most common items did not appear in the association rules, highlighting the importance of understanding item popularity versus item associations.

---

## Tools and Libraries Used
- **Python**
- **Pandas** (for data manipulation)
- **NumPy** (for random sampling)
- **MLxtend** (for Apriori Algorithm and Association Rules)

---

## Setup Instructions

### Prerequisites
- Python 3.x
- Required libraries: `pandas`, `numpy`, `mlxtend`

### Steps to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Association-Rule-Mining.git
   cd Association-Rule-Mining


2. Install the required libraries:

   ```bash
   pip install -r requirements.txt