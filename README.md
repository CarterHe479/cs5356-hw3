# cs5356-hw3


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Personal Homepage</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <header>
        <h1>My Trubute to Taylor Swift's 1989</h1>
    </header>

    <main>
        <!-- add photo -->
        <img src="images/taylor_swift.jpg" alt="Taylor Swift">

        <!-- add description -->
        <p>Taylor Swift is an American singer-songwriter. Her music spans multiple genres, including pop, country, and indie. She is known for her heartfelt lyrics and powerful performances, and has won numerous awards throughout her career.</p>

        <!-- add video -->
        <video controls width="320" height="240">
            <source src="video/TaylorSwift.MP4" type="video/mp4">
            Your browser does not support the video tag.
    </main>

    <footer>
        <p>Created by Carter He</p>
    </footer>

    <!-- add  cat image-->
     <div id="cat-image-container">
        <h2>Random Cat Image for Fun!</h2>>
        <img id="cat-image" src="" alt="Random Cat Image">
     </div>

     <script>
        const catImageContainer = document.getElementById('cat-image-container');
        const catImage = document.getElementById('cat-image');

        fetch('https://api.thecatapi.com/v1/images/search')
           .then(response => {
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                return response.json();
            })
           .then(data => {
                const catImageUrl = data[0].url;
                // set the src attribute of the cat image to the URL of the random cat image
                catImage.src = catImageUrl;
            })
           .catch(error => {
                console.error('There has been a problem with your fetch operation:', error);
                catImageContainer.innerHTML = '<p>Sorry, could not load a cat image. Please try again later.</p>';
            });        
     </script>
    
</body>

</html>


1. Use an HTML element we haven't talked about
The <video> element is a tag used in HTML to embed video content. By adding the controls attribute, users can easily play, pause, and adjust the volume of the video. The <source> sub-element specifies the location and type of the video file, and supports many common video formats. When the <video> element is not supported by the browser, fallback content within the tag, such as hint text, is displayed to the user. The use of the <video> element allows for a visual representation of the video content on a web page, enhancing the user experience, and is especially suited for presenting music videos, promotional videos, and other scenarios.

2. Use a CSS property we haven't talked about 
The "filter" attribute is a CSS property used to apply graphical effects, such as blurring or color shifting, to elements. The grayscale function used here is one of the many functions of the "filter" attribute that can change the degree of gray in an image. By setting different parameter values, you can gradually transition an image from normal color to full grayscale. Combined with the transition attribute, when the mouse hovers over the image, the value of the filter attribute changes, and the image is transformed into grayscale mode with a smooth transition effect, which enhances the interactivity and visual effect of the page. In addition to grayscale, the filter attribute also supports blur, sepia, and many other functions to create a variety of visual representations.
