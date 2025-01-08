
# Spam Classification using DistilBERT

This project fine-tunes a pre-trained DistilBERT model for spam classification. The dataset includes labeled text messages ("ham" and "spam") that are tokenized and processed for training.

---

## Code Breakdown

### 1. Importing Libraries and Reading Data
```python
import pandas as pd

df = pd.read_csv(r'C:\Users\sawan\OneDrive\Desktop\AI\SMSSpamCollection.txt', sep='\t', names=["label", "message"])
print(df.head())
```
- Reads a tab-separated file (`SMSSpamCollection.txt`).
- Columns:
  - `label`: Indicates "ham" (non-spam) or "spam".
  - `message`: The actual text of the message.

---

### 2. Dataset Shape
```python
df.shape
```
- Returns the number of rows and columns in the dataset.

---

### 3. Separating Features and Labels
```python
X = list(df['message'])
y = list(df['label'])
```

---

### 4. Encoding Labels
```python
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
y = le.fit_transform(y)
print(y)
```
- Converts labels (`ham`, `spam`) into numeric values (0, 1).

---

### 5. Splitting Data
```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

---

### 6. Tokenizing Data
```python
from transformers import DistilBertTokenizer
tokenizer = DistilBertTokenizer.from_pretrained('distilbert-base-uncased')

train_encodings = tokenizer(X_train, truncation=True, padding=True, max_length=512)
test_encodings = tokenizer(X_test, truncation=True, padding=True, max_length=512)
```

---

### 7. Converting Data to TensorFlow Dataset
```python
import tensorflow as tf
train_dataset = tf.data.Dataset.from_tensor_slices((dict(train_encodings), y_train))
test_dataset = tf.data.Dataset.from_tensor_slices((dict(test_encodings), y_test))
```

---

### 8. Loading Pre-trained DistilBERT Model
```python
from transformers import TFDistilBertForSequenceClassification
model = TFDistilBertForSequenceClassification.from_pretrained("distilbert-base-uncased", num_labels=2)
```

---

### 9. Defining Training Arguments
```python
from transformers import TFTrainingArguments
training_args = TFTrainingArguments(
    output_dir='./results',
    num_train_epochs=2,
    per_device_train_batch_size=8,
    per_device_eval_batch_size=16,
    warmup_steps=500,
    weight_decay=0.01,
    logging_dir='./logs',
    logging_steps=10
)
```

---

### 10. Fine-tuning the Model
```python
from transformers import TFTrainer

trainer = TFTrainer(
    model=model,
    args=training_args,
    train_dataset=train_dataset,
    eval_dataset=test_dataset
)
trainer.train()
```

---

### 11. Evaluating the Model
```python
results = trainer.evaluate()
print(results)
```

---

## Summary
This project:
1. Loads and preprocesses a labeled dataset.
2. Fine-tunes a pre-trained DistilBERT model for spam classification.
3. Evaluates the model's performance.

Feel free to modify or extend the code for your specific use case!

---
