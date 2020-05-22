## Python 🐍
### For Web Development 🌐

🎬 [**San**](https://sanspace.in)thosh Srinivasan

---

#### What is Python?

  - General Purpose Programming Language
  - Interpreted
  - High Level

---

#### Why Python?

  - Readable
    - no curly braces!
    - no semicolons!
    - indentation
  - Beginner Friendly
  - Batteries Included

---

#### A bit of Python

```python
print('Hello World!')
```

output:
`Hello World!`

---

#### A byte of Python

```python
def say_hello(name):
    print(f'Hello {name}!')

say_hello("San")
```

output:
`Hello San!`

---

#### What is Web Development?

  - Making Websites (or Web Apps)

---

#### What are Websites made of?

  - HTML
  - CSS
  - JavaScript

<small>*oversimplified</small>

---

#### Some jargons

  - Server
    - Computer where the code lives
    - Someone else's Computer

  - Client
    - Computer you use to visit a website
    - Your Computer

---

#### More jargons

  - Front-End
    - Client Side Code
    - What you see in the Browser
    - HTML, CSS and Javascript
  
  - Back-end
    - Server side code
    - Python, Javscript, Java and etc.

---

#### HTML

###### HyperText Markup Language

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Example</title>
</head>
<body>
    <h1>HTML is Awesome!</h1>
    <p>Thank you, Tim Berners Lee!</p>
</body>
</html>

```

---

#### Closer Look

```html
<body>
    <h1>HTML is Awesome!</h1>
    <p>Thank you, Tim Berners Lee!</p>
</body>
```

---

#### Anatomy of an HTML element

![Anatomy of an HTML element](img/anatomy-of-html.png)

<small>Image courtesy: [MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Anatomy_of_an_HTML_element)</small>

---

#### CSS - Cascading Style Sheets

Syntax:

```css
selector {
  property: value;
}

```

Example:

```css
h1 {
    color: red;
    font-size: 5em;
}
```

CSS adds styling to the web pages. 💄

---

#### HTML with CSS

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>HTML is Awesome!</h1>
    <p>Thank you, Tim Berners Lee!</p>
</body>
</html>
```

---

#### Web Frameworks

  - Simplify server-side development
  - Every Language has a Web Framework!

---

#### Python Web Frameworks

  - Flask
    - Micro Framework
    - Beginner Friendly

  - Django
    - Batteries Included
    - Opinionated

---

#### Flask - Getting Started

##### Pre-requisites

 - Python 3
 - `pip install Flask`

---

#### Flask

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```

How to Run?

```
$ export FLASK_APP=hello.py
$ flask run
 * Running on http://127.0.0.1:5000/
```

---

#### Routing

```python
@app.route('/')
def index():
    return 'Index Page'

@app.route('/hello')
def hello():
    return 'Hello, World'
```

---

#### Variable Rules

```python
from markupsafe import escape

@app.route('/user/<username>')
def show_user_profile(username):
    # show the user profile for that user
    return 'User %s' % escape(username)

@app.route('/post/<int:post_id>')
def show_post(post_id):
    # show the post with the given id, the id is an integer
    return 'Post %d' % post_id

@app.route('/path/<path:subpath>')
def show_subpath(subpath):
    # show the subpath after /path/
    return 'Subpath %s' % escape(subpath)
```

---

#### HTTP Methods

```python
from flask import request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        return do_the_login()
    else:
        return show_the_login_form()
```

---

#### Rendering Templates

Flask Code:
```python
from flask import render_template

@app.route('/hello/')
@app.route('/hello/<name>')
def hello(name=None):
    return render_template('hello.html', name=name)
```

Template:
```html
<!doctype html>
<title>Hello from Flask</title>
{% if name %}
  <h1>Hello {{ name }}!</h1>
{% else %}
  <h1>Hello, World!</h1>
{% endif %}
```

---

#### Redirects and Errors

```python
from flask import abort, redirect, url_for

@app.route('/')
def index():
    return redirect(url_for('login'))

@app.route('/login')
def login():
    abort(401)
    this_is_never_executed()
```

---

#### Questions?

---

#### Credits

  - MDN - [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn)
  - Flask [Official Docs](https://flask.palletsprojects.com/en/1.1.x/quickstart/)
