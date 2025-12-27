# Ex.08 Design of Interactive Image Gallery
## Date:

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```py
projects's urls.py

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include('gallery.urls')),
]

app's urls.py

from django.urls import path
from . import views

urlpatterns = [
    path('',views.index,name='index'),
]

views.py 

from django.shortcuts import render

def index(request):
    return render(request,'gallery/index.html')
```
```css
/* CSS file */
body {
    text-align: center;
    color: aliceblue;
    background-color: black;
    font-family: Arial, sans-serif;
    height: 100vh;
}

.gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
    margin-top: 30px;
    height: 600px;
}

.gallery img {
    width: 200px;
    height: 150px;
    border-radius: 8px;
    cursor: pointer;
    transition: transform 0.3s;
    height: 350px;
    width: 430px;
}

.gallery img:hover {
    transform: scale(1.1);
}

/* Modal styles */
.modal {
    display: none;
    position: fixed;
    z-index: 2;
    padding-top: 80px;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.8);
}

.modal-content {
    margin: auto;
    display: block;
    width: 60%;
    border-radius: 10px;
}

.close {
    position: absolute;
    top: 30px;
    right: 50px;
    color: white;
    font-size: 40px;
    cursor: pointer;
}
```
```js
// JS file
// Get modal elements
var modal = document.getElementById("modal");
var modalImg = document.getElementById("modalImage");
var closeBtn = document.getElementsByClassName("close")[0];

// Open image in modal when clicked
document.querySelectorAll(".gallery img").forEach(img => {
    img.addEventListener("click", () => {
        modal.style.display = "block";
        modalImg.src = img.src;
    });
});

// Close modal on click
closeBtn.onclick = function() {
    modal.style.display = "none";
};

// Close modal when clicking outside image
modal.onclick = function(e) {
    if (e.target === modal) {
        modal.style.display = "none";
    }
};
```

## OUTPUT:

<img width="529" height="295" alt="image" src="https://github.com/user-attachments/assets/87f5ae1d-503d-4ed5-a2e2-63a614896c8f" />


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
