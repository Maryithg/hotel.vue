<template>
  <div id="app">
    <nav>
      <router-link to="/">Inicio</router-link>
      <router-link to="/rooms">Habitaciones</router-link>
      <router-link to="/contact">Contacto</router-link>
      <router-link to="/extreme-sports">Deportes Extremos</router-link>
      <router-link to="/services">Servicios</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style scoped>
body {
  margin: 0;
  font-family: 'Arial', sans-serif;
}

nav {
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(90deg, rgba(0,36,61,1) 0%, rgba(0,91,150,1) 50%, rgba(0,36,61,1) 100%);
  padding: 15px 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  font-size: 20px;
}

nav a {
  color: white;
  text-decoration: none;
  margin: 0 15px;
  font-size: 1.1em;
  padding: 10px 15px;
  border-radius: 5px;
  transition: background-color 0.3s, transform 0.3s;
}

nav a:hover {
  background-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

#app {
  padding-top: 70px; 
}
</style>

