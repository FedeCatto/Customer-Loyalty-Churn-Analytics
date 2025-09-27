# 📊 Marketing Analytics Project  

## 🔎 Summary  
This project applies **Marketing Analytics** techniques to optimize customer loyalty, retention, and engagement.  
Using **RFM segmentation**, **churn prediction**, and **sentiment analysis**, we analyzed customer behavior, identified at-risk users, and designed **data-driven retention campaigns** with measurable ROI.  
The work follows the **CRISP-DM methodology**, from data collection to deployment, ensuring a structured and business-oriented approach.  

---

## 📌 Overview  
This project presents a **data-driven approach to marketing optimization** with the goal of increasing customer loyalty, retention, and engagement.  
By combining RFM segmentation, churn prediction models, and sentiment analysis, we analyzed customer behavior, identified at-risk users, and designed actionable marketing strategies.  

The project follows the **CRISP-DM methodology**, ensuring a rigorous process from data collection to deployment, and ultimately supporting targeted campaigns that deliver measurable business value.  

---

## 🎯 Business Scope  
We addressed three key research questions:  
- How can **average customer value** be increased?  
- How can **seasonal churn** be reduced?  
- How can **negative experiences** be identified and mitigated to improve satisfaction and retention?  

---

## 🗂️ Data Sources  
Data was provided by **Snowit** and included:  
- **Users & Profiles**: demographics, preferences, activity  
- **Cards**: membership type, validity, status  
- **Orders & Transactions**: items, frequency, promotions, payments  
- **Reviews**: labeled and unlabeled customer feedback for sentiment analysis  

---

## 🔧 Data Preparation  
- Standardized data types (dates, booleans, categoricals)  
- Handled missing values via removal, median imputation, or placeholders  
- Removed sparse/uninformative columns  

---

## 📊 Analytical Models  

### 1. RFM Segmentation  
- Metrics: **Recency, Frequency, Monetary**  
- Quartile-based scoring → segmentation into categories (*Champions, Loyal, At Risk, Lost*)  
- **Insights**: most customers required activation, while high-value segments required personalized premium campaigns  

### 2. Churn Prediction  
- Focus: **active users from the previous season**  
- Feature engineering from orders, profiles, and cards  
- **Best model**: LightGBM (AUC = 0.82, Recall = 89%, Precision = 81%)  
- **Key churn drivers**: city, last purchase recency, number of cards, membership type, acquisition channel  

### 3. Sentiment Analysis  
- Preprocessing: stopword removal, lemmatization, TF-IDF features  
- Models tested: Logistic Regression, Random Forest, CNN  
- **Best model**: Logistic Regression (Accuracy = 82%)  
- **Insights**: majority of reviews positive; negatives mostly about customer support and food  

---

## 📈 Campaign Design  

### Personalized Retention Campaign  
- **Target audience**: ~10,700 predicted churners  
- **Promotion**: 20% voucher, with adaptive discounts based on RFM segment (10–30%)  
- **Messaging**: personalized by sentiment (empathetic, encouraging, rewarding)  

### Economics & ROI  
- **Costs**: €25,571 (outreach + vouchers)  
- **Incremental Retention**:  
  - Conservative (+5%) → 433 users saved  
  - Realistic (+15%) → 1,299 users saved  
  - Optimistic (+25%) → 2,165 users saved  
- **Net Gains**: €71k – €458k depending on uplift scenario  
- **ROI**: +278% to +1792%, highly profitable in all cases 🚀  

---

## 🚀 Deployment  
- **When**: Start of new season (peak churn period), monthly updates  
- **How**: Integration of churn scores and sentiment insights into campaign targeting  
- **Why**: Maximizes retention and loyalty while optimizing marketing costs  

---

## 🔮 Future Work  
- Improve churn model recall to minimize lost revenue  
- Conduct **A/B testing** for personalized messaging  
- Leverage **seasonal patterns** for dynamic campaign design  

---

## 👥 Authors  
- **Borserini Riccardo**  
- **Federico Cesare Cattò**  
