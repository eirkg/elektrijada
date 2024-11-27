<!DOCTYPE html>
<html lang="sr">
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Електријада КГ</title>

  <!-- Slick CSS -->
  <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"/>
  <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick-theme.css"/>

  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }

    .slider-container {
      width: 80%;
      margin: 20px auto;
    }

    .slick-slide {
      text-align: center;
    }

    .slick-slide img, .slick-slide iframe {
      max-width: 100%;
      height: auto;
      margin: 0 auto;
    }
  </style>
</head>
<body>

<h1 style="text-align: center;">Галерија</h1>
<div class="slider-container">
  <div id="gallery" class="slider"></div>
</div>

<!-- Slick JS -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>

<script>
  const folderId = '1_rQYqr1xVrXL_D_ZgkSiEhKMn1MdrPRu';
  const API_KEY = '{{API_KEY}}';

  fetch(`https://www.googleapis.com/drive/v3/files?q='${folderId}'+in+parents&key=${API_KEY}&fields=files(id,name,mimeType)`)
    .then(response => response.json())
    .then(data => {
      const gallery = document.getElementById('gallery');

      data.files.forEach(file => {
        const mimeType = file.mimeType;
        let element;

        if (mimeType.startsWith('video/')) {
          element = document.createElement('iframe');
          element.src = `https://drive.google.com/file/d/${file.id}/preview`;
          element.allow = "autoplay; encrypted-media";
          element.style = "width: 100%; height: 300px;";
        } else if (mimeType.startsWith('image/')) {
          element = document.createElement('img');
          element.src = `https://lh3.googleusercontent.com/d/${file.id}`;
          element.alt = file.name;
        }

        if (element) {
          const slide = document.createElement('div');
          slide.appendChild(element);
          gallery.appendChild(slide);
        }
      });

      // Initialize Slick Slider
      $('.slider').slick({
        dots: true,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        autoplay: true,
        autoplaySpeed: 3000,
      });
    })
    .catch(error => console.error('Error fetching files:', error));
</script>

</body>
</html>
