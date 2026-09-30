# Encoding Techniques in Machine Learning

Encoding means converting data, especially **categorical data**, into numbers so that Machine Learning models can understand it.

---

# 🇬🇧 English

## 1. Label Encoding

Each category gets a number.

```text
Red   → 0
Blue  → 1
Green → 2
```

✅ Simple and fast.

⚠️ Problem: The model may think `2 > 1 > 0`.

Best for:

* Binary categories
* Tree-based models
* Sometimes ordinal data

---

## 2. One-Hot Encoding

Creates a new column for each category.

Example:

```text
Color = Red, Blue, Green
```

Becomes:

```text
        Red  Blue  Green
Red      1    0      0
Blue     0    1      0
Green    0    0      1
```

✅ No fake order between categories.

⚠️ Can create many columns.

Best for:

* Nominal categorical data
* Small number of categories

---

## 3. Ordinal Encoding

Used when categories have a real order.

Example:

```text
Low    → 0
Medium → 1
High   → 2
```

✅ Keeps the natural order.

Best for:

* Low / Medium / High
* Beginner / Intermediate / Advanced
* Small / Medium / Large

---

## 4. Binary Encoding

First converts categories into numbers, then converts those numbers into binary.

Example:

```text
A → 1 → 001
B → 2 → 010
C → 3 → 011
```

✅ Uses fewer columns than One-Hot Encoding.

Best for:

* Features with many categories

---

## 5. Frequency Encoding

Replace each category with how often it appears.

Example:

```text
Country
Egypt → 50 times
USA   → 30 times
UK    → 20 times
```

Encoding:

```text
Egypt → 50
USA   → 30
UK    → 20
```

✅ Easy and reduces number of columns.

⚠️ Different categories can have the same frequency.

---

## 6. Count Encoding

Very similar to Frequency Encoding.

Replace each category with the number of times it appears.

```text
Cat → 100
Dog → 70
Bird → 20
```

Difference:

* Count Encoding → number of occurrences
* Frequency Encoding → sometimes uses proportion/percentage

---

## 7. Target Encoding

Replace each category with the average target value for that category.

Example:

```text
City       Average Sales
Cairo      500
Alex       350
Giza       400
```

Then:

```text
Cairo → 500
Alex  → 350
Giza  → 400
```

✅ Powerful when there are many categories.

⚠️ Can cause data leakage and overfitting if used incorrectly.

---

## 8. Hash Encoding

Uses a hash function to convert categories into a fixed number of columns.

✅ Good for very large numbers of categories.

⚠️ Different categories may sometimes map to the same value.

Best for:

* Large datasets
* High-cardinality features

---

## 9. Embedding Encoding

Common in Deep Learning.

Each category is represented by a vector of numbers.

Example:

```text
Cat → [0.2, 0.8, -0.1]
Dog → [0.7, 0.1, 0.5]
```

✅ Can learn relationships between categories.

Used in:

* Neural Networks
* NLP
* Recommendation Systems

---

# Quick Comparison

| Encoding Type | Main Idea                 | Best Use                        |
| ------------- | ------------------------- | ------------------------------- |
| Label         | Category → Number         | Simple categories               |
| One-Hot       | Category → New Columns    | Small number of categories      |
| Ordinal       | Category → Ordered Number | Ordered categories              |
| Binary        | Category → Binary         | Many categories                 |
| Frequency     | Category → Frequency      | Medium/high cardinality         |
| Count         | Category → Count          | Frequency-based information     |
| Target        | Category → Target Mean    | Predictive categorical features |
| Hashing       | Category → Hash           | Very high cardinality           |
| Embedding     | Category → Vector         | Deep Learning                   |

---

## Easy Way to Remember

**Label** = Number

**One-Hot** = New columns

**Ordinal** = Ordered numbers

**Binary** = Binary representation

**Frequency** = How often?

**Count** = How many?

**Target** = Average target

**Hashing** = Hash function

**Embedding** = Learned vector

---

# 🇪🇬 الشرح بالعربي

الـ **Encoding** يعني إننا نحول البيانات، خصوصًا الـ Categorical Data، إلى أرقام علشان الـ Machine Learning Model يقدر يفهمها.

---

## 1. Label Encoding

كل Category بنعطيها رقم.

```text
Red   → 0
Blue  → 1
Green → 2
```

✅ بسيط وسريع.

⚠️ المشكلة إن الـ Model ممكن يفهم إن:

```text
2 > 1 > 0
```

رغم إن الألوان أصلًا مفيش بينهم ترتيب.

---

## 2. One-Hot Encoding

بنعمل Column جديد لكل Category.

مثلاً:

```text
Red
Blue
Green
```

تبقى:

```text
        Red  Blue  Green
Red      1    0      0
Blue     0    1      0
Green    0    0      1
```

✅ مفيش ترتيب وهمي بين البيانات.

⚠️ ممكن يعمل Columns كتير جدًا.

---

## 3. Ordinal Encoding

بنستخدمه لما يكون فيه ترتيب حقيقي بين الـ Categories.

مثلاً:

```text
Low    → 0
Medium → 1
High   → 2
```

هنا الترتيب منطقي فعلًا.

---

## 4. Binary Encoding

بنحول الـ Categories لأرقام وبعد كده نحول الأرقام لـ Binary.

مثلاً:

```text
A → 1 → 001
B → 2 → 010
C → 3 → 011
```

✅ بيعمل Columns أقل من One-Hot.

مفيد لما يكون عندك Categories كتير.

---

## 5. Frequency Encoding

بنستبدل الـ Category بعدد أو نسبة ظهوره في الـ Dataset.

مثلاً:

```text
Egypt → ظهر 50 مرة
USA   → ظهر 30 مرة
UK    → ظهر 20 مرة
```

فتصبح:

```text
Egypt → 50
USA   → 30
UK    → 20
```

---

## 6. Count Encoding

بنستبدل كل Category بعدد مرات ظهوره.

مثلاً:

```text
Cat  → 100
Dog  → 70
Bird → 20
```

الفرق البسيط:

```text
Count     = عدد مرات الظهور
Frequency = ممكن تكون نسبة أو تكرار
```

---

## 7. Target Encoding

بنستبدل كل Category بمتوسط الـ Target الخاص بيها.

مثلاً لو الـ Target هو Sales:

```text
Cairo → Average Sales = 500
Alex  → Average Sales = 350
Giza  → Average Sales = 400
```

فتصبح:

```text
Cairo → 500
Alex  → 350
Giza  → 400
```

✅ قوي جدًا.

⚠️ لازم نستخدمه بحذر لأنه ممكن يعمل Data Leakage.

---

## 8. Hash Encoding

بيستخدم Hash Function علشان يحول Categories كثيرة إلى عدد ثابت من الأعمدة.

✅ مناسب جدًا لو عندك عدد ضخم من الـ Categories.

⚠️ أحيانًا Categories مختلفة ممكن تتحول لنفس القيمة.

---

## 9. Embedding Encoding

يستخدم كثيرًا في Deep Learning.

كل Category يتم تمثيلها بمجموعة أرقام.

مثلاً:

```text
Cat → [0.2, 0.8, -0.1]

Dog → [0.7, 0.1, 0.5]
```

✅ الـ Model يتعلم العلاقات بين الـ Categories.

يستخدم في:

* Neural Networks
* NLP
* Recommendation Systems

---

# الفرق بسرعة

| النوع              | الفكرة                      |
| ------------------ | --------------------------- |
| Label Encoding     | كل Category = رقم           |
| One-Hot Encoding   | كل Category = Column        |
| Ordinal Encoding   | رقم حسب الترتيب             |
| Binary Encoding    | تحويل لـ Binary             |
| Frequency Encoding | حسب تكرار الـ Category      |
| Count Encoding     | عدد مرات ظهورها             |
| Target Encoding    | متوسط الـ Target            |
| Hash Encoding      | استخدام Hash Function       |
| Embedding          | تمثيل كل Category بـ Vector |

---

# أسهل طريقة للحفظ

**Label = رقم**

**One-Hot = Columns**

**Ordinal = ترتيب**

**Binary = 0 و 1**

**Frequency = ظهر قد إيه**

**Count = ظهر كام مرة**

**Target = متوسط الـ Target**

**Hashing = Hash Function**

**Embedding = Vector بيتعلمه الـ Model**

---

## 🎥 Video Explanation

[Watch the video explanation](PUT-YOUR-VIDEO-LINK-HERE)
