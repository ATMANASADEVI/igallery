# Ex.08 Design of Interactive Image Gallery
## Date:15/12/2024

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
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif, sans-serif sans-serif;
            margin: 0;
            padding: 0;
            background-color: lavender;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        h1 {
            margin: 20px 0;
            color: black;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 1200px;
            width: 100%;
            padding: 20px;
        }

        .gallery-item {
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer;
            position: relative;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s, filter 0.3s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(0.8);
        }

        .gallery-item .caption {
            position: absolute;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            color: #fff;
            width: 100%;
            text-align: center;
            padding: 10px;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .gallery-item:hover .caption {
            opacity: 1;
        }

        #lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        #lightbox img {
            max-width: 90%;
            max-height: 90%;
        }

        #lightbox .close {
            position: absolute;
            top: 20px;
            right: 20px;
            color: #fff;
            font-size: 30px;
            cursor: pointer;
        }

        footer {
            background-color: #333;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
            width: 100%;
            position: fixed;
            bottom: 0;
        }
    </style>
</head>
<body>
    <h1>Interactive Photo Gallery</h1>
    <div class="gallery">
        <div class="gallery-item">
            <img src="Max.jpg" alt="Image 1">
            <div class="caption">Maxine</div>
        </div>
        <div class="gallery-item">
            <img src="Dustin.jpg" alt="Image 2">
            <div class="caption">Dustin</div>
        </div>
        <div class="gallery-item">
            <img src="Steve harringtom.jpg" alt="Image 3">
            <div class="caption">Steve harringtom</div>
        </div>
        <div class="gallery-item">
            <img src="Mike Eleven.jpg" alt="Image 4">
            <div class="caption">Mike Eleven</div>
        </div>
        <div class="gallery-item">
            <img src="Nancy.jpg" alt="Image 6">
            <div class="caption">Nancy</div>
        </div>
   </div>

    <div id="lightbox">
        <span class="close">&times;</span>
        <img src="" alt="Enlarged Image">
    </div>

    <footer>
        <p>Designed and Developed by AT Manasa Devi</p>
    </footer>

    <script>
        const galleryItems = document.querySelectorAll('.gallery-item img');
        const lightbox = document.getElementById('lightbox');
        const lightboxImg = lightbox.querySelector('img');
        const closeBtn = lightbox.querySelector('.close');

        galleryItems.forEach(item => {
            item.addEventListener('click', () => {
                lightbox.style.display = 'flex';
                lightboxImg.src = item.src;
            });
        });

        closeBtn.addEventListener('click', () => {
            lightbox.style.display = 'none';
        });

        lightbox.addEventListener('click', (event) => {
            if (event.target === lightbox) {
                lightbox.style.display = 'none';
            }
        });
    </script>
</body>
</html>
 
```
## OUTPUT:
![alt text](<Screenshot (76).png>)
## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
