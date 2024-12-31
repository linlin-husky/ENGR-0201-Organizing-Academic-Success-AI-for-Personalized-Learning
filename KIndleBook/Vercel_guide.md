The project is well-structured, but I have identified minor formatting issues and provided refinements for clarity and consistency. Here's the corrected and formatted version:

---

# **Branching Narrative Game Using Python and Flask**

## **Project Overview**

**Objective**: Create a branching narrative game where user choices shape the story.  
**Tools Used**:  
- Python  
- Flask (lightweight web framework)  

**Structure**:  
- Multiple story paths and endings based on user decisions.

---

## **Navigation Flow**

**Starting Point (`index.html`)**:  
You are presented with two choices:  
- Enter the Forest  
- Explore the Cave  

**Forest Path (`forest.html`)**:  
- Follow the Path (leads to the treasure)  
- Turn Back (returns to the starting point)  

**Cave Exploration (`cave.html`)**:  
- Exit Quickly (returns to the starting point)  
- Continue Deeper (leads to the treasure)  

**Treasure Found (`treasure.html`)**:  
- The final page congratulates you on finding the hidden treasure.  

---

## **Setup Instructions**

### 1. **Install Python**  
Download and install Python from [https://www.python.org/downloads/](https://www.python.org/downloads/).  

Verify the installation:  
```bash
python --version
```

### 2. **Set Up a Virtual Environment**  
Create and activate a virtual environment:  
```bash
python -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
```

### 3. **Install Flask**  
Install Flask in your virtual environment:  
```bash
pip install Flask
```

### 4. **Create Project Folder Structure**  

```plaintext
branching_narrative/
├── app.py
├── templates/
│   ├── index.html
│   ├── forest.html
│   ├── cave.html
│   └── treasure.html
```

---

## **Project Code**

### 1. **`app.py`**
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/forest')
def forest():
    return render_template('forest.html')

@app.route('/cave')
def cave():
    return render_template('cave.html')

@app.route('/treasure')
def treasure():
    return render_template('treasure.html')

if __name__ == '__main__':
    app.run(debug=True)
```

---

### 2. **HTML Templates**

#### **`index.html`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Branching Narrative Game</title>
    <style>
        body {
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTBUQg6Cl0Zb2y1a_4V5sG0ZhcvPRa4OgLUrA&s');
            background-size: cover;
            background-repeat: no-repeat;
            color: white;
            text-align: center;
            padding-top: 20%;
            font-family: Arial, sans-serif;
        }
        a {
            color: yellow;
            font-size: 1.2em;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <h1>You are standing at the entrance of a dark forest.</h1>
    <p>Do you want to enter the forest or explore the cave nearby?</p>
    <a href="/forest">Enter the Forest</a><br>
    <a href="/cave">Explore the Cave</a>
</body>
</html>
```

#### **`forest.html`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Forest Path</title>
    <style>
        body {
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3LF-TEmhchJpnDUD4Rcr3C3qCc_aKgUgITw&s');
            background-size: cover;
            background-repeat: no-repeat;
            color: white;
            text-align: center;
            padding-top: 20%;
            font-family: Arial, sans-serif;
        }
        a {
            color: yellow;
            font-size: 1.2em;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <h1>You venture into the forest and find a hidden path.</h1>
    <p>Do you follow the path or turn back?</p>
    <a href="/treasure">Follow the Path</a><br>
    <a href="/">Turn Back</a>
</body>
</html>
```

#### **`cave.html`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Cave Exploration</title>
    <style>
        body {
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQN4iQbCbt1qykY3ePxhOunIx-tnZ08VUmSig&s=');
            background-size: cover;
            background-repeat: no-repeat;
            color: white;
            text-align: center;
            padding-top: 20%;
            font-family: Arial, sans-serif;
        }
        a {
            color: yellow;
            font-size: 1.2em;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <h1>You enter the cave and hear strange noises.</h1>
    <p>Do you continue deeper or exit quickly?</p>
    <a href="/">Exit Quickly</a><br>
    <a href="/treasure">Continue Deeper</a>
</body>
</html>
```

#### **`treasure.html`**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Treasure Found!</title>
    <style>
        body {
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_mFyWTnNz3Irsn7q58a7N22FIJ_iPAY6ivQ&s');
            background-size: cover;
            background-repeat: no-repeat;
            color: white;
            text-align: center;
            padding-top: 20%;
            font-family: Arial, sans-serif;
        }
        a {
            color: yellow;
            font-size: 1.2em;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <h1>Congratulations! You discovered a hidden treasure!</h1>
    <p>The adventure was worth it. Play again?</p>
    <a href="/">Start Over</a>
</body>
</html>
```

---

## **Running the Game**

1. **Launch the Flask App**  
   In your project folder, run:
   ```bash
   python app.py
   ```

2. **Open the Game in Your Browser**  
   Navigate to:
   [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

3. **Play the Game**  
   - Make choices and see where the story takes you!  
   - Branches lead to different outcomes based on your decisions.  

This version ensures consistency, correct formatting, and removes any potential errors.
