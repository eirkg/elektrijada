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
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>


</head>

## Обавештења 2024-2025

* Званичан сајт [електријаде](https://www.elektrijada.net/).
* Нема за сад ништа јбг.



## Одлазак 2024

* (Не)Званични координатори за науку и спорт:

<table style="width: 400px; text-align: center; border: none;">
  <tr>
    <td style="padding-right:20px;padding-top:10px">
      <img src="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/koordinator_nauka.png" width="150" />
      <br />
      <a href="https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=lazar@uni.kg.ac.rs">Лазар Илић</a>
    </td>
    <td style="padding-left:20px;padding-top: 10px;">
      <img src="https://raw.githubusercontent.com/eirkg/elektrijada/refs/heads/main/.slike/koordinator_sport.png" width="150" />
      <br />
      <a href="https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=radosavljevicdanilo333@gmail.com">Данило Радосављевић</a>
    </td>
  </tr>
</table>




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



<!-- Галерија која слајдује -->
<div id="gallery-container" style="width: 100%; height: 100%; overflow: hidden; background: #000;">
  <div id="image-slider" class="slick-slider" style="width: 100%; margin: 0 auto;"></div>
</div>

<!-- Fullscreen Overlay Modal -->
<div id="fullscreenModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.8); z-index: 1000;">
  <span id="closeModal" style="color: white; font-size: 30px; position: absolute; top: 20px; right: 20px; cursor: pointer;">&times;</span>
  <img id="fullscreenImage" src="" alt="" style="width: 100%; height: auto; margin: 0; display: block; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);">
</div>

<script>
  const folderId = '1_rQYqr1xVrXL_D_ZgkSiEhKMn1MdrPRu';
  const API_KEY = '{{API_KEY}}';

  // Отварање слике у fullscreen модалу
  function openFullscreenImage(imageSrc) {
    const modal = document.getElementById('fullscreenModal');
    const fullscreenImage = document.getElementById('fullscreenImage');
    modal.style.display = 'block';
    fullscreenImage.src = imageSrc;
  }

  // Затварање fullscreen модала
  document.getElementById('closeModal').onclick = function() {
    document.getElementById('fullscreenModal').style.display = 'none';
  };

  // Fetch слика са Google Drive-а
  fetch(`https://www.googleapis.com/drive/v3/files?q='${folderId}'+in+parents&key=${API_KEY}&fields=files(id,name,mimeType)`)
    .then(response => response.json())
    .then(data => {
      const gallery = document.getElementById('image-slider');
      data.files.forEach(file => {
        if (file.mimeType.startsWith('image/')) {
          const img = document.createElement('img');
          img.src = `https://lh3.googleusercontent.com/d/${file.id}`;
          img.alt = file.name;
          img.style = "width: 100%; height: auto; object-fit: cover; cursor: pointer;";

          // Додавање слике у слајдер
          img.onclick = function() {
            openFullscreenImage(`https://lh3.googleusercontent.com/d/${file.id}`);
          };

          gallery.appendChild(img);
        }
      });

      // Покретање Slick слајдера
      $(document).ready(function(){
        $('#image-slider').slick({
          infinite: true,  // Бесконачно клизање
          slidesToShow: 1, // Покажи једну слику по слајду
          slidesToScroll: 1, // Клизни један по један
          autoplay: true,  // Аутоматско репродуковање
          autoplaySpeed: 2000,  // Брзина аутоматског клизања (у милисекундама)
          dots: true, // Додавање тачака за навигацију
          arrows: true, // Додавање стрелица за навигацију
        });
      });
    })
    .catch(error => console.error('Error fetching files:', error));
</script>

<style>
  /* Стиловање слајдера */
  .slick-slider {
    width: 100%;
    margin: 0 auto;
  }

  .slick-slide img {
    width: 100%;
    height: auto;
  }

  /* Стиловање за fullscreen слике */
  #fullscreenImage {
    width: 100%;
    height: auto;
    object-fit: cover;
  }
</style>