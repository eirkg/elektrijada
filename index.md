<head>
  <meta charset="utf-8">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; img-src 'self' https://drive.google.com;">
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


<div id="gallery" style="display: flex; flex-wrap: wrap;"></div>

<script>
  const folderId = '1_rQYqr1xVrXL_D_ZgkSiEhKMn1MdrPRu';
  const API_KEY = '{{API_KEY}}';

  fetch(`https://www.googleapis.com/drive/v3/files?q='${folderId}'+in+parents&key=${API_KEY}&fields=files(id,name,mimeType)`)
    .then(response => response.json())
    .then(data => {
      const gallery = document.getElementById('gallery');
      data.files.forEach(file => {
        if (file.mimeType.startsWith('video/')) {
          const iframe = document.createElement('iframe');
          iframe.src = `https://drive.google.com/file/d/${file.id}/preview`;
          iframe.width = "300";
          iframe.height = "200";
          iframe.style = "margin: 5px; border: none;";
          iframe.allow = "autoplay; encrypted-media";
          iframe.allowFullscreen = true;
          gallery.appendChild(iframe);
        } else if (file.mimeType.startsWith('image/')) {
          const img = document.createElement('img');
          img.src = `https://drive.google.com/uc?export=view&id=${file.id}`;

          img.alt = file.name;
          img.style = "width: 150px; height: auto; margin: 5px;";
          gallery.appendChild(img);
        }
      });
    })
    .catch(error => console.error('Error fetching files:', error));
</script>

