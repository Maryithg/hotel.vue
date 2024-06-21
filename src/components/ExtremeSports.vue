<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <div class="extreme-sports">
    <h1>Deportes Extremos</h1>
    <div class="sport" v-for="sport in sports" :key="sport.id">
      <div class="sport-icon">
        <i :class="sport.icon"></i>
      </div>
      <div class="sport-image">
        <img :src="sport.image" :alt="sport.name" />
      </div>
      <div class="sport-details">
        <h2>{{ sport.name }}</h2>
        <p>{{ sport.description }}</p>
        <p>Nivel de Dificultad: {{ sport.difficulty }}</p>
        <p>Precio: {{ sport.price }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sports: [
        {
          id: 1,
          name: "Paracaidismo",
          description: "Experiencia emocionante.",
          difficulty: "Alta",
          price: "$300",
          image: "./img/skydiving.jpeg",
          icon: "fas fa-parachute-box"
        },
        {
          id: 2,
          name: "Buceo",
          description: "Explora el mundo submarino.",
          difficulty: "Media",
          price: "$200",
          image: "./img/diving.jpeg",
          icon: "fas fa-water"
        },
        {
          id: 3,
          name: "Escalada",
          description: "Desafía las alturas.",
          difficulty: "Alta",
          price: "$250",
          image: "./img/climbing.jpeg",
          icon: "fas fa-mountain"
        },
        {
          id: 4,
          name: "Rafting",
          description: "Aventura en rápidos.",
          difficulty: "Alta",
          price: "$180",
          image: "./img/rafting.jpeg",
          icon: "fas fa-water"
        },
        {
          id: 5,
          name: "Safari",
          description: "Encuentro con la vida salvaje.",
          difficulty: "Baja",
          price: "$400",
          image: "./img/safari.jpeg",
          icon: "fas fa-binoculars"
        },
        {
          id: 6,
          name: "Ciclismo de montaña",
          description: "Rutas y senderos desafiantes.",
          difficulty: "Media",
          price: "$150",
          image: "./img/mountain_biking.jpeg",
          icon: "fas fa-bicycle"
        },
        {
          id: 7,
          name: "Surf",
          description: "Domina las olas.",
          difficulty: "Media",
          price: "$120",
          image: "./img/surfing.jpeg",
          icon: "fas fa-water"
        },
        {
          id: 8,
          name: "Senderismo",
          description: "Conexión con la naturaleza.",
          difficulty: "Baja",
          price: "$50",
          image: "./img/hiking.jpeg",
          icon: "fas fa-hiking"
        },
        {
          id: 9,
          name: "Esquí",
          description: "Deslízate por la nieve.",
          difficulty: "Alta",
          price: "$300",
          image: "./img/skiing.jpeg",
          icon: "fas fa-skiing"
        },
        {
          id: 10,
          name: "Kayak",
          description: "Navega en aguas tranquilas.",
          difficulty: "Media",
          price: "$100",
          image: "./img/kayaking.jpeg",
          icon: "fas fa-water"
        },
      ],
    };
  },
};
</script>

<style scoped>
.extreme-sports {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  padding: 20px;
  background-color: #f9f9f9;
}

.extreme-sports h1 {
  width: 100%;
  text-align: center;
  font-size: 2.5em;
  color: #333;
  margin-bottom: 40px;
  font-family: "Merriweather", serif;
  font-weight: 750;
}

.sport {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: calc(33.333% - 40px);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  position: relative;
}

.sport:hover {
  transform: translateY(-10px);
  box-shadow: 0 6px 20px rgba(18, 112, 253, 0.15);
}

.sport-icon {
  position: absolute;
  top: 15px;
  left: 15px;
  background-color: #fff;
  border-radius: 50%;
  padding: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  z-index: 1;
}

.sport-icon i {
  font-size: 1.5em;
  color: #17a2b8;
}

.sport-image {
  position: relative;
  overflow: hidden;
}

.sport-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.sport:hover .sport-image img {
  transform: scale(1.1);
}

.sport-details {
  padding: 20px;
}

.sport h2 {
  font-size: 1.8em;
  color: #17a2b8;
  margin-bottom: 10px;
}

.sport p {
  color: #666;
  font-size: 1.1em;
  margin-bottom: 5px;
}

@media (max-width: 768px) {
  .sport {
    width: calc(50% - 20px);
  }
}

@media (max-width: 480px) {
  .sport {
    width: 100%;
  }
}
</style>
