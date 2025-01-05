
# **Getting Started with Streamlit**

This guide explains how to use a Streamlit app to introduce users to Streamlit and its features. The content includes the main code, steps to run the app locally, and a detailed breakdown of the app.

---

## **Main Code**

Below is the complete Streamlit app code:

```python
import streamlit as st
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Title of the App
st.title("Getting Started with Streamlit")

# Introduction
st.header("What is Streamlit?")
st.write("""
Streamlit is a Python library that makes it easy to build interactive, data-driven web applications for data science, machine learning, and other Python-based projects. 
You can turn your Python scripts into fully functional web apps with minimal effort.
""")

# Key Features of Streamlit
st.header("Why Use Streamlit?")
st.write("""
Streamlit provides several key features that make it unique:
1. **Simplicity**: Build apps with just Python. No need for HTML, CSS, or JavaScript.
2. **Interactivity**: Add sliders, buttons, text inputs, and other UI elements easily.
3. **Data Visualization**: Integrate seamlessly with libraries like Matplotlib, Plotly, and Altair.
4. **Deployment**: Share your apps with others easily using Streamlit Community Cloud or other deployment methods.
""")

# Code Example
st.header("How Simple is Streamlit?")
st.code("""
import streamlit as st

st.title("Hello, Streamlit!")
st.write("This is my first Streamlit app.")
""", language="python")
st.write("With just a few lines of code, you can create a web app!")

# Interactive Widgets
st.header("Explore Streamlit Widgets")
st.write("Let's explore some basic widgets:")

# Text Input
name = st.text_input("What's your name?")
if name:
    st.write(f"Hello, {name}! 👋")

# Slider
age = st.slider("Select your age:", 0, 100, 25)
st.write(f"You selected: {age} years old.")

# Checkbox
agree = st.checkbox("Do you like Streamlit?")
if agree:
    st.write("That's awesome! 🎉")

# Radio Buttons
experience = st.radio(
    "How would you rate your experience with Streamlit?",
    ["Beginner", "Intermediate", "Advanced"]
)
st.write(f"You selected: {experience}")

# Data Visualization
st.header("Data Visualization with Streamlit")
st.write("Here's an example of displaying a simple chart:")

# Example Data
data = pd.DataFrame(
    np.random.randn(50, 3),
    columns=["Feature 1", "Feature 2", "Feature 3"]
)

# Line Chart
st.line_chart(data)

# Matplotlib Plot
st.subheader("Using Matplotlib")
fig, ax = plt.subplots()
ax.hist(data["Feature 1"], bins=15, alpha=0.7)
st.pyplot(fig)

# File Upload
st.header("Working with Files")
st.write("You can upload files and work with them in Streamlit.")
uploaded_file = st.file_uploader("Upload a CSV file", type=["csv"])
if uploaded_file:
    df = pd.read_csv(uploaded_file)
    st.write("Here's the uploaded data:")
    st.dataframe(df)

# Sidebar Example
st.sidebar.header("Sidebar Example")
st.sidebar.write("This is a sidebar. Use it for navigation or displaying additional information.")
sidebar_option = st.sidebar.radio(
    "Choose a feature to explore:",
    ["Introduction", "Widgets", "Data Visualization", "File Upload"]
)
st.sidebar.write(f"You selected: {sidebar_option}")

# Summary
st.header("Summary")
st.write("""
Streamlit is a powerful, yet simple tool for creating web apps in Python. 
With its intuitive API and focus on interactivity, it's a great choice for beginners and professionals alike.
""")

# Resources
st.write("Want to learn more? Check out these resources:")
st.markdown("- [Streamlit Documentation](https://docs.streamlit.io)")
st.markdown("- [Streamlit GitHub Repository](https://github.com/streamlit/streamlit)")
st.markdown("- [Streamlit Community](https://discuss.streamlit.io)")

st.write("Happy coding! 🎉")
```

---

## **How to Run the App Locally**

1. **Install Streamlit**:  
   First, install Streamlit using pip:
   ```bash
   pip install streamlit
   ```

2. **Save the Code**:  
   Save the above code in a file, for example, `app.py`.

3. **Run the App**:  
   Use the following command to run the Streamlit app:
   ```bash
   streamlit run app.py
   ```

4. **View the App**:  
   After running the command, Streamlit will open your app in a browser. If it doesn’t open automatically, copy the URL provided in the terminal (e.g., `http://localhost:8501`) and paste it into your browser.

---

## **Explanation of the Code**

This app is divided into several sections:

### **1. Introduction**
- Introduces Streamlit and its purpose.
- Uses `st.title()`, `st.header()`, and `st.write()` to display text.

### **2. Why Use Streamlit?**
- Lists the key features of Streamlit using `st.write()` and markdown-style text.

### **3. Code Example**
- Demonstrates how easy it is to build a Streamlit app with a minimal code snippet.
- Uses `st.code()` to display the code in a readable format.

### **4. Widgets**
- Introduces interactive widgets like `st.text_input()`, `st.slider()`, `st.checkbox()`, and `st.radio()`.

### **5. Data Visualization**
- Shows how to create visualizations using:
  - Streamlit's `st.line_chart()`.
  - Matplotlib's `plt.hist()` for custom plots.

### **6. File Upload**
- Demonstrates how to upload and process files with `st.file_uploader()`.

### **7. Sidebar Navigation**
- Adds a sidebar for navigation using `st.sidebar.radio()`.

### **8. Summary and Resources**
- Concludes with a summary and links to helpful Streamlit resources.

---

## **Conclusion**
This Streamlit app introduces users to Streamlit's features and capabilities in a hands-on way. By following the guide, users can:
1. Learn how to build Streamlit apps.
2. Explore interactive widgets and visualizations.
3. Understand the simplicity and power of Streamlit.

Happy coding! 🎉
