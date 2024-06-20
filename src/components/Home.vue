<template>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
  <div class="home">
    <section class="welcome">
      <h1>Bienvenidos! <br>
        Hotel Serenidad
      </h1>
      <img src="/img/hotel.jpeg" alt="Hotel">
      <p>Disfruta de nuestros servicios de primera categoría, que incluyen piscinas, restaurantes, spas y mucho más.</p>
      <button @click="exploreMore">Descubre más opciones.</button>
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
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  padding: 40px;
  text-align: center;
  max-width: 800px;
  width: 100%;
}

.welcome h1 {
  font-size: 2.5em;
  color: #333;
  margin-bottom: 20px;
  font-family: "Merriweather", serif;
  font-weight: 750;
  font-style: normal;
}

.welcome img {
  max-width: 100%;
  border-radius: 10px;
  margin-bottom: 20px;
}

.welcome p {
  font-size: 1.2em;
  color: #666;
  line-height: 1.5;
  margin-bottom: 30px;
}

button {
  background: linear-gradient(90deg, rgb(1, 66, 112) 0%, rgb(1, 101, 168) 50%, rgb(23, 151, 243) 100%);
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 1.1em;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

button:hover {
  transform: translateY(-2px);
}
</style>
