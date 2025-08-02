## 🔁 Naive Bayes in ML: What Happens During Training vs Testing

---

### 🏋️‍♀️ Training Phase (Learning from Data)

In the training phase, the Naive Bayes model **learns the probabilities it needs to make predictions**.

#### What it does:
1. **Calculate Priors**:
   - Computes the prior probability of each class.
   - Example:
     ```
     P(Spam) = (# of spam emails) / (total emails)
     ```

2. **Calculate Likelihoods**:
   - For each feature, it estimates the likelihood:
     ```
     P(feature_i | class)
     ```
   - This depends on the type of Naive Bayes:
     - **GaussianNB**: estimates mean and variance of feature per class.
     - **MultinomialNB**: counts frequency of features per class (e.g. word counts).
     - **BernoulliNB**: computes probability of feature being 1 or 0 given the class.
     - **CategoricalNB**: uses frequency of category values per class.

➡️ At the end of training, the model **stores these probabilities** — but it doesn't store the actual training data.

---

### 🧪 Testing Phase (Making Predictions)

In the testing (inference) phase, the model uses what it learned to **predict the class of new/unseen samples**.

#### What it does for each test sample:
1. **Take observed features** from the input sample:
---
X = [x1, x2, ..., xn]

---

2. **Compute Posterior Probability for each class**:
- Uses Bayes’ Rule:
  ```
  P(Class | X) ∝ P(x1 | Class) * P(x2 | Class) * ... * P(Class)
  ```
- Multiplies the likelihood of each feature given the class, with the prior of the class.

3. **Choose the class with the highest posterior**:
- This becomes the predicted class label.

---

### 🧠 Example (MultinomialNB on Email Data)

#### Training:
- Learns:
---
P(Spam) = 0.3

P(Not Spam) = 0.7

P("free" | Spam) = 0.8

P("free" | Not Spam) = 0.1

---

#### Testing:
- New email has word "free".
- Computes:
P(Spam | "free") ∝ 0.8 * 0.3 = 0.24
P(Not Spam | "free") ∝ 0.1 * 0.7 = 0.07

---

- Predicts: `Spam`, because 0.24 > 0.07

---

## 📌 Summary

| Phase     | What Happens                                                         |
|-----------|----------------------------------------------------------------------|
| Training  | Learn **prior probabilities** and **feature likelihoods** from data |
| Testing   | Use those learned values to compute **posterior probabilities** for new samples and make predictions |

✅ The Naive Bayes model **does not memorize the training data**, it just stores the statistical summaries it needs.

