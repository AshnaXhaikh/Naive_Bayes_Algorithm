Let’s **clear one thing up once and for all**:

> When we say "Gaussian for continuous data" or "Bernoulli for binary data",
> we are always talking about the **features (independent variables)** — **not the target**.

---

## 🔍 Why?

Naive Bayes is a **generative model**. It learns how the **features behave given each class**.

### So, it models:

$$
P(x_i \mid \text{Class})
$$

* Where $x_i$ are your **features** (like word count, age, yes/no, etc.)
* And "Class" is your **target** (like spam/ham, positive/negative, etc.)

---
