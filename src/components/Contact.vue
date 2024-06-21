<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <div class="contact">
    <h1>Contacto</h1>
    <div class="contact-info">
      <p><i class="fas fa-map-marker-alt"></i> Dirección: Calle Principal 12, San Gil, Colombia</p>
      <p><i class="fas fa-phone"></i> Teléfono: +57 313 6724 213</p>
      <p><i class="fas fa-envelope"></i> Email: <a href="mailto:HotelSerenidad@gmail.com">HotelSerenidad@gmail.com</a></p>
    </div>
    <h2>Formulario de Contacto</h2>
    <form @submit.prevent="submitForm">
      <label for="name"><i class="fas fa-user"></i> Nombre:</label>
      <input type="text" id="name" v-model="form.name" placeholder="Tu nombre">
      <label for="email"><i class="fas fa-envelope"></i> Email:</label>
      <input type="email" id="email" v-model="form.email" placeholder="Tu email">
      <label for="message"><i class="fas fa-comment"></i> Mensaje:</label>
      <textarea id="message" v-model="form.message" placeholder="Tu mensaje"></textarea>
      <button type="submit"><i class="fas fa-paper-plane"></i> Enviar</button>
    </form>
    <h2>Ubicación</h2>
    <iframe src="https://maps.google.com/maps?q=hotel%20location&t=&z=13&ie=UTF8&iwloc=&output=embed"></iframe>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      alert('Mensaje enviado');
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

.contact {
  padding: 20px;
  max-width: 800px;
  margin: 0 auto;
  background: linear-gradient(135deg, #ffffff 0%, #a0a0a0 100%);
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  font-family: 'Poppins', sans-serif;
}

.contact h1 {
  font-size: 2.5em;
  text-align: center;
  color: #333;
  margin-bottom: 20px;
  font-family: "Merriweather", serif;
  font-weight: 700;
}

.contact-info {
  text-align: center;
  margin-bottom: 40px;
}

.contact-info p {
  font-size: 1.2em;
  color: #333;
  line-height: 1.5;
  margin: 10px 0;
}

.contact-info p i {
  margin-right: 10px;
  color: #17a2b8;
}

.contact-info p a {
  color: #098ca0;
  text-decoration: none;
}

.contact h2 {
  font-size: 2em;
  color: #0d0d0d;
  margin-top: 40px;
  margin-bottom: 20px;
  text-align: center;
}

form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

form label {
  font-size: 1.1em;
  color: #333;
}

form input, form textarea {
  padding: 10px;
  font-size: 1em;
  border: 2px solid #333;
  border-radius: 10px;
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: border-color 0.3s ease;
}

form input:focus, form textarea:focus {
  border-color: #0198af;
}

button {
  align-self: center;
  padding: 10px 30px;
  background: linear-gradient(90deg, #00528d 0%, #1b7ff1 100%);
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1.2em;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #138496;
}

iframe {
  margin-top: 20px;
  width: 100%;
  height: 450px;
  border: none;
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}
</style>
