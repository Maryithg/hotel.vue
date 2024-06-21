<template>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <div class="home">
    <section class="welcome">
      <div class="welcome-text">
        <h1>Bienvenidos a <br> Hotel Serenidad</h1>
        <p>Disfruta de una estancia inolvidable con nuestras instalaciones de lujo.</p>
        <button @click="exploreMore">Descubre más <i class="fas fa-chevron-right"></i></button>
      </div>
      <div class="welcome-image">
        <img src="/img/hotel.jpeg" alt="Hotel Serenidad">
      </div>
    </section>
  </div>
</template>

<script>
export default {
  methods: {
    exploreMore() {
      this.$router.push('/rooms');
    }
  }
}
</script>

<style scoped>
.home {
  background-color: #f5f5f5;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
}

.welcome {
  background-color: #fff;
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 100px;
  max-width: 1400px;
  width: 100%;
}

.welcome-text {
  flex: 1;
  text-align: left;
}

.welcome h1 {
  font-size: 3em;
  color: #333;
  margin-bottom: 20px;
  font-family: "Merriweather", serif;
  font-weight: 700;
  line-height: 1.2;
}

.welcome p {
  font-size: 1.2em;
  color: #666;
  line-height: 1.6;
  margin-bottom: 30px;
}

button {
  background: linear-gradient(90deg, rgb(1, 66, 112) 0%, rgb(1, 101, 168) 50%, rgb(23, 151, 243) 100%);
  color: white;
  padding: 12px 24px;
  border: none;
  border-radius: 5px;
  font-size: 1.1em;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

button:hover {
  background-color: #0968a4;
  transform: translateY(-3px);
}

button i {
  margin-left: 5px;
}

.welcome-image {
  flex: 1;
  margin-left: 40px;
  text-align: center;
}

.welcome-image img {
  max-width: 100%;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

@media (max-width: 768px) {
  .welcome {
    flex-direction: column;
    text-align: center;
  }

  .welcome-text, .welcome-image {
    margin-left: 0;
    margin-right: 0;
  }
}
</style>
