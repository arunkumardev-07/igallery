# Ex.08 Design of Interactive Image Gallery
## Name: Arunkumar P
## Reg No: 212222040016
## Date: 14/05/2025

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
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INTERACTIVE IMAGE GALLERY</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color:pink;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        .title {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 42px;
            font-style:oblique;
            color:cyan;
            z-index: 1;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }

        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(370px, 1fr));
            gap: 10px;
            padding: 20px;
            max-width: 1200px;
            width: 100%;
        }

        .gallery-item img {
            width: 100%; 
            height: 300px; 
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .gallery-item img:hover {
            transform: scale(1.30);
            cursor: pointer;
        }

        .slider {
            display: none;
            position: fixed;
            z-index: 2;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 100%;
            text-align: center;
        }

        .slider img {
            width: 90%;
            max-width: 800px;
            border-radius: 10px;
            transition: opacity 0.5s ease;
        }

        .arrow {
            cursor: pointer;
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 40px;
            color: white;
            user-select: none;
            padding: 10px;
        }

        .arrow.left {
            left: 10px;
            color: aqua;
        }

        .arrow.right {
            right: 10px;
            color: aqua;
        }

        .arrow:hover {
            color: lightgray;
        }

        .close-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: rgba(0, 0, 0, 0.6);
            color: rgb(0, 255, 251);
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 20px;
            border-radius: 5px;
            display: none;
        }

        .close-btn:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }
        .container
        {
          text-align:center;
          right: 600px;
          position: absolute;
          bottom: 8px;
          background-color: white;
          color: black;
          width: cover;
          height: 40px;
          font-style:italic;
        }
    </style>
</head>
<body>
    <div class="title">WONDERS OF THE WORLD</div> 
    
    <div class="gallery-container">
        <div class="gallery-item">
            <img src="image1.jpg" alt="Image 1">
        </div>
        <div class="gallery-item">
            <img src="image2.jpg" alt="Image 2">
        </div>
        <div class="gallery-item">
            <img src="image3.jpg" alt="Image 3">
        </div>
        <div class="gallery-item">
            <img src="image4.jpg" alt="Static Image">
        </div>
        <div class="gallery-item">
            <img src="inage5.jpg" alt="Image 5">
        </div>
        <div class="gallery-item">
            <img src="image6.jpg" alt="Image 6">
        </div>
        <footer class="container">
        <p>&copy;DESINGED BY Renick Fabian Rajesh</p>
        </footer>
        

    </div>

    <div class="slider" id="slider">
        <button class="close-btn" id="close-btn">&#10006;</button>
        <span class="arrow left" id="prev">&#10094;</span>
        <img src="" alt="Slider Image" id="slider-img">
        <span class="arrow right" id="next">&#10095;</span>
    </div>

    <script>
        const images = document.querySelectorAll('.gallery-item img');
        const slider = document.getElementById('slider');
        const sliderImg = document.getElementById('slider-img');
        const prevBtn = document.getElementById('prev');
        const nextBtn = document.getElementById('next');
        const closeBtn = document.getElementById('close-btn');

        let currentIndex = 0;
        images.forEach((image, index) => {
            image.addEventListener('click', () => {
                slider.style.display = 'block';
                sliderImg.src = image.src;
                currentIndex = index;
                closeBtn.style.display = 'block'; 
            });
        });

        prevBtn.addEventListener('click', (e) => {
            e.stopPropagation(); 
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            sliderImg.src = images[currentIndex].src;
        });
        nextBtn.addEventListener('click', (e) => {
            e.stopPropagation(); 
            currentIndex = (currentIndex + 1) % images.length;
            sliderImg.src = images[currentIndex].src;
        });

        closeBtn.addEventListener('click', () => {
            slider.style.display = 'none';
            closeBtn.style.display = 'none';
        });

        slider.addEventListener('click', () => {
            slider.style.display = 'none';
            closeBtn.style.display = 'none';
        });
    </script>

</body>
</html>

```
## OUTPUT:
![Screenshot 2025-05-16 222806](https://github.com/user-attachments/assets/38bee414-0f73-43b2-94aa-5c2caef5ac88)
![Screenshot 2025-05-14 200939](https://github.com/user-attachments/assets/c316e648-ba1f-48fd-984d-8fa0b93673a6)
![Screenshot 2025-05-16 222935](https://github.com/user-attachments/assets/e636f2a9-38aa-4a8b-be43-5659921795fa)
![Screenshot 2025-05-16 223056](https://github.com/user-attachments/assets/12625ad1-02e7-454b-a35a-d84b24348646)
![Screenshot 2025-05-14 201015](https://github.com/user-attachments/assets/f66c23da-13ea-461c-806c-689b079cacc8)
![Screenshot 2025-05-14 201026](https://github.com/user-attachments/assets/9ecaf172-ddca-4fe1-abe2-d5fdc2bdfb47)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
