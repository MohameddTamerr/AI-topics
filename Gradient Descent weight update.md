# ➤ What is the purpose of the negative sign in the Gradient Descent weight update?

## 🇬🇧 English

The Gradient Descent weight update rule is:

```text
New Weight = Old Weight - (Learning Rate × Gradient)
```

or:

```text
w_new = w_old - η × gradient
```

### Why do we use `-`?

The **gradient tells us the direction where the error increases the fastest**.

But our goal is to **reduce the error (Loss)**.

So, we move in the **opposite direction** of the gradient.

That's why we use the negative sign `-`.

```text
Gradient → Error increases

We want → Error decreases

So we move ← opposite to the gradient
```

### Simple Example

Suppose:

```text
Old Weight = 5
Learning Rate = 0.1
Gradient = 2
```

Then:

```text
New Weight = 5 - (0.1 × 2)

New Weight = 4.8
```

The weight moves from **5 → 4.8** to help reduce the error.

### What if the gradient is negative?

For example:

```text
Gradient = -2
```

Then:

```text
New Weight = 5 - (0.1 × -2)

New Weight = 5.2
```

So the weight increases.

The `-` does **not always mean the weight decreases**.

It means:

> Move in the opposite direction of the gradient.

### Easy way to remember

**Gradient = direction of increasing error**

**Negative sign = go in the opposite direction**

**Goal = minimize the error**

---

# 🇪🇬 الشرح بالعربي

قاعدة تحديث الـ Weight في **Gradient Descent** هي:

```text
New Weight = Old Weight - (Learning Rate × Gradient)
```

### ليه بنستخدم علامة `-`؟

الـ **Gradient** بيقولنا الاتجاه اللي الـ **Error بيزيد فيه بأسرع شكل**.

لكن إحنا مش عايزين نزود الـ Error.

إحنا عايزين **نقلل الـ Loss / Error**.

عشان كده بنمشي في **الاتجاه العكس للـ Gradient**.

وده سبب وجود علامة السالب `-`.

```text
Gradient → الاتجاه اللي الـ Error بيزيد فيه

إحنا عايزين → الـ Error يقل

يبقى نمشي ← عكس الـ Gradient
```

### مثال بسيط

لو عندنا:

```text
Old Weight = 5
Learning Rate = 0.1
Gradient = 2
```

نعمل:

```text
New Weight = 5 - (0.1 × 2)

New Weight = 4.8
```

يعني الـ Weight اتحرك من:

```text
5 → 4.8
```

في اتجاه يساعدنا نقلل الـ Error.

### طب لو الـ Gradient سالب؟

مثلاً:

```text
Gradient = -2
```

يبقى:

```text
New Weight = 5 - (0.1 × -2)

New Weight = 5.2
```

هنا الـ Weight **زاد**.

يعني علامة `-` مش معناها إن الـ Weight لازم يقل كل مرة.

معناها:

> اتحرك عكس اتجاه الـ Gradient.

### أسهل طريقة تحفظها

**Gradient = اتجاه زيادة الـ Error**

**Negative Sign (-) = امشي في الاتجاه العكس**

**Gradient Descent = نحاول نقلل الـ Error**

### 🎥 Video Explanation

[Watch the video explanation](PUT-YOUR-VIDEO-LINK-HERE)
