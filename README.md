# Ex.08 Design of Interactive Image Gallery
# Date:05.10.2025
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
    <style>
        body {
            margin: 0;
            font-family:fantasy;
            background: #111;
            color: white;
            letter-spacing: 0.1cm;
        }

        h1 {
            text-align: center;
            margin: 20px ;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 100px;
            padding: 40px;
        }

        .gallery img {
            width: 250px;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: 4px 4px 9px white;
            transition: transform 0.5s ease;
        }

        .gallery img:hover {
            transform: scale(1.4);
        }
        .modal {
            display: none;
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(9, 2, 2, 0.9);
            justify-content: center;
            align-items: center;
            
        }

        .modal img {
            max-width: 70%;
            max-height: 70%;
            border-radius: 15px;
            box-shadow:2px 2px 2px white
            ,-2px -2px 2px white
        }

        .close {
            position: absolute;
            top: 30px;
            right: 50px;
            color: rgb(38, 240, 234);
            font-size: 40px;
            font-weight: bolder;
            cursor: pointer;
    
        }

        .close:hover {
            color: lightpink;
        }
    </style>
</head>
<body>
    <h1>OUR GALLERY</h1>
    <div class="gallery">
        <img src="{% static 'photo1.jpg' %}" alt="Photo1" onclick="openModal(this)">
        <img src="{% static 'photo3.jpg' %}" alt="Photo2" onclick="openModal(this)">
        <img src="{% static 'photo2.jpg' %}" alt="Photo3" onclick="openModal(this)">
        <img src="{% static 'photo4.jpg' %}" alt="Photo4" onclick="openModal(this)">
        <img src="{% static 'photo5.jpg' %}" alt="Photo5" onclick="openModal(this)">
    </div>
    <div id="myModal" class="modal">
        <span class="close" onclick="closeModal()">&times;</span>
        <img id="modalImage" src="">
    </div>

    <script>
        function openModal(img) {
            const modal = document.getElementById("myModal");
            const modalImg = document.getElementById("modalImage");
            modal.style.display = "flex";
            modalImg.src = img.src;
        }

        function closeModal() {
            document.getElementById("myModal").style.display = "none";
        }
    </script>

</body>
</html>

views.py 

from django.shortcuts import render
def p1(request):
    return render(request,'home.html')

urls.py

from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.p1,name="home"),
]
```
# OUTPUT:
 
![alt text](<Screenshot 2025-10-05 231922.png>)
![alt text](<Screenshot 2025-10-05 232002.png>)
![alt text](<Screenshot 2025-10-05 232022.png>)
![alt text](<Screenshot 2025-10-05 232036.png>)
# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
