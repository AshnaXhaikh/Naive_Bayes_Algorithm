## 🗺️ Mapping Bayes Terms to Machine Learning (Naive Bayes)

| Bayes Term   | ML Equivalent                          | Explanation                                                                 |
|--------------|-----------------------------------------|-----------------------------------------------------------------------------|
| **Prior**    | `P(Class)`                              | The overall probability of each class in the training data (before features are seen) |
| **Evidence** | `X` (Features/Input data)               | The input features we observe in a sample (e.g., word counts, age, yes/no) |
| **Likelihood** | `P(Feature | Class)`                  | Probability of seeing a specific feature value given the class             |
| **Posterior**| `P(Class | X)`                          | The updated probability of a class after seeing the features (final prediction) |

---

### 🔁 In Summary:

- **Prior** → What the model assumes about the class before looking at the features.  
  → Based on class distribution in the training data.

- **Evidence** → The features (X) of a sample.  
  → The input we give to the model for prediction.

- **Likelihood** → How likely each feature value is under each class.  
  → Learned from training data.

- **Posterior** → What the model believes about the class **after** seeing the evidence.  
  → Final prediction is based on highest posterior probability.

