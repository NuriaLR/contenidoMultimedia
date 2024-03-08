 <template>
  <div class="container">
    <div class="title-container">
      <h1>PAISAJES NATURALES DE ESPAÑA</h1>
    </div>
    <div class="content-container">
      <div class="card-container">
        <div class="card" v-for="(card, index) in cards" :key="index">
          <img :src="card.image" alt="Card Image">
          <div class="card-content">
            <h2>{{ card.title }}</h2>
            <p>{{ card.description }}</p>
          </div>
        </div>
      </div>
      <div class="media-container">
        <video autoplay muted class="responsive-video">
          <source src="/video/video.mp4" type="video/mp4">
        </video>
        <audio controls autoplay >
          <source src="/audio/sonido.mp3" type="audio/mp4">
        </audio>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: 'Las Médulas',
          description: 'El Bierzo, León.',
          image: '../public/img/las-medulas.jpg'
        },
        {
          title: 'Nacimiento río Mundo',
          description: 'Riópar, Albacete',
          image: '../public/img/rio-mundo.jpg'
        },
        {
          title: 'Monumento natural de los Mallos de Riglos, Agüero y Peña Rueba',
          description: 'Huesca',
          image: '../public/img/monumen-huesca.jpg'
        },
        {
          title: 'Playa de las Catedrales',
          description: 'Galicia',
          image: '../public/img/playa-catedrales.jpg'
        },
        {
          title: 'Selva de Irati',
          description: 'Navarra',
          image: '../public/img/selva-Irati.jpg'
        },
        {
          title: 'Parque nacional de Timanfaya',
          description: 'Lanzarote',
          image: '../public/img/timanfaya.jpg'
        },
      ]
    };
  }
}
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Divide el contenedor en dos columnas */
  gap: 20px; /* Espacio entre las columnas */
}

.title-container {
  grid-column: 1 / span 2; /* El título abarca las dos columnas */
}

.content-container {
  display: flex;
  flex-direction: column;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start; /* Alinea las tarjetas a la izquierda */
  align-items: center;
  flex: 1; /* Las tarjetas ocupan todo el espacio disponible */
}

.card {
  flex: 0 0 calc(33.33% - 20px); 
  margin: 10px; 
  display: flex;
  flex-direction: column;
  border: 1px solid #ccc; /* Añade un borde de 1px sólido y gris a cada tarjeta */
  border-radius: 8px;
  overflow: hidden;
}

.card img {
  width: 100%;
  height: auto;
}

.card-content {
  padding: 20px;
}

.media-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

@media (max-width: 768px) {
  .card {
    flex: 0 0 calc(50% - 20px); 
  }
}
</style>
