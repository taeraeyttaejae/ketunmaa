---
layout: default
title: Galleria
---

<style>
/* Lightbox styles */
.lightbox {
  display: none;
  position: fixed;
  z-index: 999;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.9);
  cursor: pointer;
}

.lightbox.active {
  display: flex;
  justify-content: center;
  align-items: center;
}

.lightbox img {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
  cursor: default;
}

.lightbox-close {
  position: absolute;
  top: 20px;
  right: 30px;
  font-size: 40px;
  color: white;
  cursor: pointer;
  font-weight: bold;
  transition: color 0.3s;
  z-index: 1000;
}

.lightbox-close:hover {
  color: #ccc;
}

.gallery-item {
  cursor: pointer;
}

.gallery-item:hover {
  opacity: 0.9;
}
</style>

## Galleria

Kuvia yhdistyksemme tapahtumista ja kylältä. Jos haluat kuvasi tänne, ota yhteyttä puheenjohtajaan!

### Kyläkuvat

<div class="gallery">
  <div class="gallery-item" onclick="openLightbox('assets/images/kukka.jpg')">
    <img src="assets/images/kukka.jpg" alt="Peltomaisemaa">
    <div class="gallery-caption">Peltomaisemaa</div>
  </div>
  <div class="gallery-item" onclick="openLightbox('assets/images/seppele.jpg')">
    <img src="assets/images/seppele.jpg" alt="Seppele">
    <div class="gallery-caption">Maisemaa seppeleen läpi</div>
  </div>
</div>

<!-- Lightbox container -->
<div id="lightbox" class="lightbox" onclick="closeLightbox()">
  <span class="lightbox-close" onclick="closeLightbox()">&times;</span>
  <img id="lightbox-img" src="" alt="" onclick="event.stopPropagation()">
</div>

<script>
function openLightbox(imgSrc) {
  const lightbox = document.getElementById('lightbox');
  const lightboxImg = document.getElementById('lightbox-img');
  lightboxImg.src = imgSrc;
  lightbox.classList.add('active');
  document.body.style.overflow = 'hidden'; // Prevent scrolling
}

function closeLightbox() {
  const lightbox = document.getElementById('lightbox');
  lightbox.classList.remove('active');
  document.body.style.overflow = ''; // Re-enable scrolling
}

// Close lightbox with Escape key
document.addEventListener('keydown', function(event) {
  if (event.key === 'Escape') {
    closeLightbox();
  }
});
</script>

---

*Kaikki kuvat © Ketunmaan - Selkäsenkylän kyläyhdistys ry*
