# Tech Skill Recommendation Model using Apriori Algorithm (Unsupervised Machine Learning)

## 📌 Overview
This project implements a **Skill Recommendation System** using the **Apriori Algorithm**, an unsupervised machine learning technique used for association rule mining. The model analyzes existing skill patterns and recommends the next set of skills a user should learn based on their current skillset.

This system is integrated into **PrepVault**, an AI-powered student success platform, to help engineering students make smarter learning decisions aligned with industry trends.

---

## 🚀 Problem Statement
Students often struggle to decide:
- What skills to learn next
- Which technologies are relevant in the industry
- How to align their learning with placement requirements

This project solves the problem by:
- Analyzing real-world developer data
- Finding relationships between skills
- Recommending relevant next skills intelligently

---

## 🧠 Approach

We use the **Apriori Algorithm**, which is an **unsupervised learning technique** used to find frequent itemsets and generate association rules.

### Key Idea:
If many users who know Skill A and Skill B also know Skill C, then:
👉 A + B → C (Recommended Skill)

---

## 📊 Dataset Used
- **Source:** Kaggle  
- **Dataset:** Stack Overflow Developer Survey 2024  
- Link: https://www.kaggle.com/datasets/joebeachcapital/stack-overflow-annual-developer-survey-2024  

### Dataset Contains:
- Developer skills
- Technologies used
- Programming languages
- Tools & frameworks

---

## ⚙️ Data Preprocessing

Steps performed:
1. Extract relevant skill columns from dataset  
2. Clean and normalize data  
3. Convert data into transactional format  
   - Each row = Set of skills of a developer  
4. Apply One-Hot Encoding  
   - Convert skills into binary format (1 = present, 0 = absent)

---

## 🔍 Apriori Algorithm Implementation

### Steps:
1. Generate frequent itemsets using minimum support  
2. Identify combinations of skills frequently occurring together  
3. Generate association rules using:
   - **Support**
   - **Confidence**
   - **Lift**

### Example Rule:
{Python, SQL} → {Machine Learning}


Meaning:
Users with Python and SQL are likely to learn Machine Learning next.

---

## 📈 Model Training

The model was trained using:
- Apriori Algorithm from `mlxtend.frequent_patterns`

### Parameters:
- Minimum Support: (e.g., 0.01)
- Minimum Confidence: (e.g., 0.5)

### Output:
- Frequent skill combinations  
- Association rules  

---

## 🏷️ Recommendation System Logic

After generating rules, recommendations are categorized into:

- 🔥 **High Demand** → Skills frequently appearing in dataset  
- 📈 **Trending** → Skills with high lift/confidence  
- ✅ **Recommended** → Skills strongly related to user's current skills  

---

## 🔄 Integration with PrepVault

The trained model is integrated into PrepVault:

### Flow:
1. User adds skills in profile  
2. Skills are sent to recommendation engine  
3. Model matches patterns using Apriori rules  
4. Suggested skills are returned  

### Output:
- Personalized skill suggestions  
- Learning guidance  
- Industry-relevant recommendations  

---

## 🛠️ Tech Stack

- Python  
- Pandas  
- NumPy  
- mlxtend (Apriori Algorithm)  
- PostgreSQL (via Supabase)  
- React / Next.js (Frontend Integration)  

---

## 📊 Example Output

Input Skills: Java, DSA


Recommended Skills: 
Spring Boot (Recommended)
System Design (High Demand)
Microservices (Trending)


---

## 🔐 Advantages

- No labeled data required (Unsupervised Learning)  
- Works on real-world developer data  
- Scalable and adaptable  
- Personalized recommendations  

---

## ⚠️ Limitations

- Depends on dataset quality  
- Cannot capture deep learning patterns like neural networks  
- Static unless retrained with new data  

---

## 🔮 Future Improvements

- Add deep learning-based recommendations  
- Real-time adaptive learning  
- Resume-based skill suggestions  
- Integration with job market APIs  

---

## 🤝 Conclusion

This project demonstrates how **unsupervised machine learning** can be used to solve real-world problems in education and career guidance. By leveraging the Apriori Algorithm, the system provides intelligent, data-driven skill recommendations that help students stay aligned with industry demands.

---

## ⭐ Acknowledgements

- Kaggle Dataset (Stack Overflow Survey 2024)  
- mlxtend Library  
- PrepVault Platform  

---
