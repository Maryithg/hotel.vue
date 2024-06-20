<template>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
    <div class="contact">
      <h1>Contacto</h1>
      <p>Dirección: Calle Principal 12, San Gil, Colombia</p>
      <p>Teléfono: +57 313 6724 213</p>
      <p>Email: Hotel Serenidad@gmail.com</p>
      <h2>Formulario de Contacto</h2>
      <form @submit.prevent="submitForm">
        <label for="name">Nombre:</label>
        <input type="text" id="name" v-model="form.name">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="form.email">
        <label for="message">Mensaje:</label>
        <textarea id="message" v-model="form.message"></textarea>
        <button type="submit">Enviar</button>
      </form>
      <h2>Ubicación</h2>
      <iframe src="https://maps.google.com/maps?q=hotel%20location&t=&z=13&ie=UTF8&iwloc=&output=embed" width="600" height="450"></iframe>
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
.contact {
  padding: 20px;
  max-width: 800px;
  margin: 0 auto;
  background-color: #f9f9f9;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.contact h1 {
  font-size: 2.5em;
  text-align: center;
  color: #333;
  margin-bottom: 20px;
  font-family: "Merriweather", serif;
  font-weight: 750;
  font-style: normal;
}

.contact p {
  font-size: 1.1em;
  color: #666;
  line-height: 1.5;
}

.contact h2 {
  font-size: 2em;
  color: #17a2b8;
  margin-top: 40px;
  margin-bottom: 20px;
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
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: border-color 0.3s ease;
}

form input:focus, form textarea:focus {
  border-color: #17a2b8;
}

button {
  align-self: flex-start;
  padding: 10px 20px;
  background: linear-gradient(90deg, rgb(0, 82, 141) 0%, rgba(0, 91, 150, 1) 50%, rgb(27, 127, 241) 100%);
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1.1em;
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
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}
</style>
