## Flask Application Design

### HTML Files

**index.html**
- This file will serve as the landing page of the application, where the user will input data.
- It should contain a form with the necessary input fields for serial numbers and attachment names.
- The form should have a submit button to trigger the data submission.

**results.html**
- This file will display the results of the application's data processing.
- It should contain an area where the AI prompt is displayed and an area where the AI response is displayed.

### Routes

**main.py**

```python
# Import necessary modules
from flask import Flask, render_template, request

# Create Flask application instance
app = Flask(__name__)

# Define route for index page
@app.route('/')
def index():
    return render_template("index.html")

# Define route for handling form submission
@app.route('/submit', methods=["POST"])
def submit():
    # Extract data from form
    serial_numbers = request.form.getlist("serial_number")
    attachment_names = request.form.getlist("attachment_name")

    # Query data, pass AI prompt, and get AI response (this part is not implemented in the design)

    # Render results page with AI prompt and response
    return render_template("results.html", prompt=prompt, response=response)

# Run the application
if __name__ == "__main__":
    app.run()
```

### Explanation

- The above design outlines a Flask application that takes inputs, queries data, passes AI prompts, and displays the AI responses.
- The index page presents a form for data input, which is then submitted to the `/submit` route.
- The `/submit` route extracts data from the form, processes it, and retrieves the AI response (though this part is not implemented in the design).
- Finally, the results page displays the AI prompt and response.