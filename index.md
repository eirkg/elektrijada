<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Електријада КГ</title>
  <link rel="apple-touch-icon" sizes="180x180" href="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/apple-touch-icon.png">
  <link rel="icon" type="image/png" sizes="32x32" href="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/favicon-32x32.png">
  <link rel="icon" type="image/png" sizes="16x16" href="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/favicon-16x16.png">
  <link rel="manifest" href="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/site.webmanifest">

    <!-- Open Graph Meta Tags -->
  <meta property="og:title" content="Електријада КГ">
  <meta property="og:image" content="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/android-chrome-512x512.png">
  <meta property="og:type" content="website">
  <meta property="og:site_name" content="Електријада КГ">

    
  <!-- Add favicon link -->
  <link rel="icon" href="{{ site.favicon | default: '/.slike/favicon.ico' }}" type="image/x-icon">

  <!-- Slick CSS -->
  <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"/>
  <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick-theme.css"/>

  <!-- Slick JS -->
  <!-- Slick JS -->
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>


</head>

## Обавештења 2024-2025

* Званичан сајт [електријаде](https://www.elektrijada.net/).
* (Не)Званична [пријава](https://forms.gle/5nuUU3JREufNnwBa7) за Електријаду 2025.

<!-- Данило тест комит -->

## Одлазак 2024

* (Не)Званични координатори за науку и спорт:

<table class="koordinator-tabela">
  <tr>
    <td class="koordinator-celija">
      <img class="koordinator-slika" src="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/koordinator_nauka.png" />
      <br />
      <a class="koordinator-link" href="https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=lazar@uni.kg.ac.rs">Лазар Илић</a>
    </td>
    <td class="koordinator-celija">
      <img class="koordinator-slika" src="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/koordinator_sport.png" />
      <br />
      <a class="koordinator-link" href="https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=radosavljevicdanilo333@gmail.com">Данило Радосављевић</a>
    </td>
  </tr>
</table>

<style>
  .koordinator-tabela {
    width: 30%;
    text-align: center;
    border: none;
    margin-left: 10px;
  }

  .koordinator-celija {
    padding: 10px 20px;
  }

  .koordinator-slika {
    width: 150px;
    height: auto;
  }

  .koordinator-link {
    display: inline-block;
    width: 153px;
    text-decoration: none;
  }

  @media (max-width: 400px) {
    .koordinator-tabela {
      width: 100%;
    }

    .koordinator-celija {
      display: block;
      text-align: center;
      padding: 10px 0;
    }

    .koordinator-link {
      width: auto;
    }
  }
</style>




### Остварени успеси

 * Из Крагујевца је пут Требиња пошло 16 студената и 1 професор.
 * Наши студенти су се такмичили у спортској дисциплини мушки футсал.
 * Наши студенти су се такмичили у научним дисциплинама аналогна електроника, аутоматика, информатика.
 * Освојена бронзана медаља из научне дисциплине аналогна електроника.


### Топ моменти


<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000;">
  <iframe 
      src="https://www.youtube.com/embed/6bFPemZ9j1c" 
      title="Elektrijada Official Aftermovie 2024" 
      frameborder="0" 
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
      referrerpolicy="strict-origin-when-cross-origin" 
      allowfullscreen>
  </iframe>
</div>

<div class="slider-container">
  <div id="gallery" class="slider"></div>
</div>

<!-- Fullscreen Overlay Modal -->
<div id="fullscreenModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.8); z-index: 1000;">
  <span id="closeModal" style="color: white; font-size: 30px; position: absolute; top: 20px; right: 20px; cursor: pointer; z-index: 2000;">&times;</span>
  <img id="fullscreenImage" src="" alt="" style="width: 100%; height: auto; margin: 0; display: block; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); z-index: 1000;">
</div>

<script>
  const folderId = '1_rQYqr1xVrXL_D_ZgkSiEhKMn1MdrPRu';
  const API_KEY = '{{API_KEY}}';

  // Open the image in fullscreen overlay
  function openFullscreenImage(imageSrc) {
    const modal = document.getElementById('fullscreenModal');
    const fullscreenImage = document.getElementById('fullscreenImage');
    modal.style.display = 'block';
    fullscreenImage.src = imageSrc;
  }

  // Close the fullscreen overlay
  document.getElementById('closeModal').onclick = function () {
    document.getElementById('fullscreenModal').style.display = 'none';
  };

  fetch(`https://www.googleapis.com/drive/v3/files?q='${folderId}'+in+parents&key=${API_KEY}&fields=files(id,name,mimeType)`)
    .then(response => response.json())
    .then(data => {
      const gallery = document.getElementById('gallery');

      // Sort files by name (case-insensitive)
      const sortedFiles = data.files.sort((a, b) => 
        a.name.toLowerCase().localeCompare(b.name.toLowerCase())
      );

      // Process and display files
      sortedFiles.forEach(file => {
        const mimeType = file.mimeType;
        let element;

        if (mimeType.startsWith('video/')) {
          element = document.createElement('iframe');
          element.src = `https://drive.google.com/file/d/${file.id}/preview`;
          element.allow = "autoplay; encrypted-media";
          element.style = "width: 100%; height: auto;";
          element.allowFullscreen = true;
        } else if (mimeType.startsWith('image/')) {
          element = document.createElement('img');
          element.src = `https://lh3.googleusercontent.com/d/${file.id}`;
          element.alt = file.name;
          element.style = "cursor: pointer; object-fit: cover; max-width: 100%; height: auto;";

          // Add click event for fullscreen
          element.onclick = function () {
            openFullscreenImage(element.src);
          };
        }

        if (element) {
          const slide = document.createElement('div');
          slide.style = "flex: 0 0 auto; padding: 10px;"; // Maintain proper slide structure for slider
          slide.appendChild(element);
          gallery.appendChild(slide);
        }
      });

      // Initialize Slick Slider
      $('.slider').slick({
        adaptiveHeight: true,
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

<style>
  /* General gallery styles */
  #gallery img {
    cursor: pointer;
    object-fit: cover;
    max-width: 100%;
    max-height: 420px;
    height: auto;
  }
  @media (max-width: 400px) {
  #gallery img {
    max-height: 250px; 
  }
}
  /* Fullscreen Modal */
  #fullscreenModal img {
    object-fit: contain;
  }

    .slider-container {
      width: 90%;
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

    .slick-prev:before, 
    .slick-next:before {
  color: #00FF00; /* Change arrow color */
}

</style>

<!-- Include Slick Slider CSS & JS -->
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel/slick/slick.css" />
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/slick-carousel/slick/slick-theme.css" />
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/slick-carousel/slick/slick.min.js"></script>
