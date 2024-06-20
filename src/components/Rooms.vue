<template>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">

  <div class="rooms">
    <h1>Habitaciones</h1>
    <div class="room" v-for="room in rooms" :key="room.id">
      <div class="room-image" @click="showRoomDetails(room)">
        <img :src="room.image" :alt="room.type">
        <div class="room-overlay">
          <h2>{{ room.type }}</h2>
          <div class="room-rating">
            <span v-for="n in 5" :key="n" :class="['fas', 'fa-star', { 'rated': n <= room.rating }]"></span>
          </div>
        </div>
      </div>
      <div class="room-details">
        <div class="details-top">
          <h2>{{ room.type }}</h2>
          <div class="room-icons">
            <i class="fas fa-bed"></i> {{ room.capacity }} personas
          </div>
        </div>
        <p>{{ room.description }}</p>
        <div class="details-bottom">
          <p>Precio: {{ room.price }}</p>
          <button @click="reserveRoom(room.id)">Reservar</button>
        </div>
      </div>
    </div>
    
    <div v-if="selectedRoom" class="modal" @click="closeModal">
      <transition name="modal-fade">
        <div class="modal-content" @click.stop>
          <span class="close" @click="closeModal">&times;</span>
          <img :src="selectedRoom.image" :alt="selectedRoom.type">
          <h2>{{ selectedRoom.type }}</h2>
          <div class="room-rating">
            <span v-for="n in 5" :key="n" :class="['fas', 'fa-star', { 'rated': n <= selectedRoom.rating }]"></span>
          </div>
          <p>{{ selectedRoom.description }}</p>
          <p>Precio: {{ selectedRoom.price }}</p>
          <button @click="reserveRoom(selectedRoom.id)">Reservar</button>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rooms: [
        { id: 1, type: 'Deluxe', description: 'Habitación espaciosa y elegante.', price: '$100', image: './img/standard.jpeg', rating: 5, capacity: 2 },
        { id: 2, type: 'Premium Suite', description: 'Habitación de lujo con servicios exclusivos.', price: '$200', image: './img/hotel.jpeg', rating: 4, capacity: 3 },
        { id: 3, type: 'Executive', description: 'Habitación con instalaciones de trabajo y relajación.', price: '$150', image: './img/executive.jpeg', rating: 4, capacity: 2 },
        { id: 4, type: 'Family Room', description: 'Habitación amplia ideal para familias.', price: '$120', image: './img/family.jpeg', rating: 4, capacity: 4 },
        { id: 5, type: 'Penthouse Suite', description: 'Suite en el ático con vistas panorámicas.', price: '$500', image: './img/penthouse.jpeg', rating: 5, capacity: 2 },
        { id: 6, type: 'Junior Suite', description: 'Suite más pequeña pero igualmente lujosa.', price: '$180', image: './img/junior-suite.jpeg', rating: 4, capacity: 2 },
        { id: 7, type: 'Single Room', description: 'Habitación acogedora para un solo huésped.', price: '$80', image: './img/single.jpeg', rating: 3, capacity: 1 },
        { id: 8, type: 'Double Room', description: 'Habitación cómoda para dos personas.', price: '$110', image: './img/double.jpeg', rating: 4, capacity: 2 },
        { id: 9, type: 'Presidential Suite', description: 'La habitación más lujosa y espaciosa del hotel.', price: '$600', image: './img/presidential.jpeg', rating: 5, capacity: 4 },
        { id: 10, type: 'Studio', description: 'Habitación con espacio adicional y zona de cocina.', price: '$140', image: './img/studio.jpeg', rating: 4, capacity: 2 }
      ],
      selectedRoom: null
    }
  },
  methods: {
    showRoomDetails(room) {
      this.selectedRoom = room;
    },
    reserveRoom(roomId) {
      alert(`Reserva para habitación ${roomId}`);
    },
    closeModal() {
      this.selectedRoom = null;
    }
  }
}
</script>

<style scoped>
.rooms {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 20px;
  background-color: #f9f9f9;
}

.rooms h1 {
  width: 100%;
  text-align: center;
  font-size: 2.5em;
  color: #333;
  margin-bottom: 40px;
  font-family: "Merriweather", serif;
  font-weight: 750;
}

.room {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: calc(33.333% - 40px);
  margin: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  position: relative;
}

.room:hover {
  transform: translateY(-10px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
}

.room-image {
  position: relative;
  overflow: hidden;
  cursor: pointer;
}

.room-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.room-image:hover img {
  transform: scale(1.1);
}

.room-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 10px;
  text-align: center;
  transition: opacity 0.3s ease;
  opacity: 0;
}

.room:hover .room-overlay {
  opacity: 1;
}

.room-overlay h2 {
  font-size: 1.5em;
  margin-bottom: 5px;
}

.room-rating {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.room-rating .fas {
  color: #c1c1c1; 
  font-size: 1.2em;
}

.room-rating .rated {
  color: #ffc107; 
}

.room-details {
  padding: 20px;
}

.room-details h2 {
  font-size: 1.8em;
  color: #17a2b8;
  margin-bottom: 15px;
}

.room-details p {
  color: #666;
  font-size: 1.1em;
  margin-bottom: 10px;
}

.room-icons {
  display: flex;
  align-items: center;
  color: #000000;
  font-size: 1.1em;
  margin-bottom: 10px;
}

button {
  background: linear-gradient(90deg, rgb(1, 54, 92) 0%, rgba(0, 91, 150, 1) 50%, rgb(27, 127, 241) 100%);
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 1.1em;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

button:hover {
  background-color: #218838;
  transform: translateY(-2px);
}

.modal {
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  text-align: center;
  position: relative;
  max-width: 80%;
}

.modal-content img {
  max-width: 360px;
  max-height: 260px; 
  border-radius: 10px;
  margin-bottom: 20px;
}

.modal-content .close {
  position: absolute;
  top: -8px;
  right: 10px;
  font-size: 2.5em;
  cursor: pointer;
  color: #000000;
}

@media (max-width: 768px) {
  .room {
    width: calc(50% - 40px);
  }
}
</style>
