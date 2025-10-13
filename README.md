# Ex.05 Design a Website for Server Side Processing
# Date:6.10.2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
math.html
<!DOCTYPE html>
<html>
<head>
    <title>Power Calculator</title>
</head>
<style>
    label {
        display: inline-block;
        width: 100px;
        text-align: right;
    }
    input {
        margin-bottom: 10px;
    }
    button {
        margin-top: 10px;
    }
    h2 {
        color: rgb(38, 0, 255);
    }
    h3 {
        color: rgb(255, 0, 0);
    }
    div {
        background-color: rgb(0, 255, 47);
        color: rgb(255, 0, 0);
        padding: 20px;
        border-radius: 10px;
        width: 400px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        margin-top: 50px;
    }
    h1{
        color:rgb(22, 195, 222);
        font-size: 40px;
        font-family: 'Times New Roman', Times, serif;
        margin-top: 20px;
        margin-bottom: 20px;
        text-shadow: 2px 2px 4px #000000;
        background-color: seashell;
    }

</style>
<body bgcolor="lightgreen">
    
       <center><div><h2>Power Calculation of Lamp Filament</h2>
    <form method="POST">
        {% csrf_token %}
        <label>Intensity (I):</label>
        <input type="text" name="intensity" required><br><br>

        <label>Resistance (R):</label>
        <input type="text" name="resistance" required><br><br>

        <button type="submit">Calculate Power</button>
    </form>

    {% if power is not None %}
        <h3>Result: Power (P) = {{ power }} watts</h3>
    {% endif %}
    </div>
    <h1>DONE BY INDHU</h1>
    </center>
</body>
</html>
views.py
from django.shortcuts import render

def calculate_power(request):
    power = None
    if request.method == 'POST':
        try:
            I = float(request.POST.get('intensity'))
            R = float(request.POST.get('resistance'))
            power = I ** 2 * R
        except (ValueError, TypeError):
            power = "Invalid input. Please enter numbers."
    return render(request, 'mathapp/math.html', {'power': power})
urls.py
from django.urls import path
from mathapp import views

urlpatterns = [
    path('', views.calculate_power, name='calculate_power'),
]
```

# SERVER SIDE PROCESSING:
<img width="1356" height="597" alt="Screenshot 2025-10-06 085543" src="https://github.com/user-attachments/assets/cf6a3645-161a-49a0-8b60-ea29f3b9f896" />

<img width="1638" height="749" alt="Screenshot 2025-10-06 085643" src="https://github.com/user-attachments/assets/e2a892da-ad88-4494-ac46-e66717859a49" />



# HOMEPAGE:
<img width="1919" height="970" alt="Screenshot 2025-10-13 192444" src="https://github.com/user-attachments/assets/6943d648-28c6-436d-be07-2f5045f1f103" />



# RESULT:
The program for performing server side processing is completed successfully.
