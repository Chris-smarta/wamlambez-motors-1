<template>
  <div class="home-page">
    <h1>Welcome to Our Website!</h1>
    <p>Explore our features and discover what we have to offer.</p>
    <div class="buttons">
      <button @click="goToAbout">About Us</button>
      <button @click="goToServices">Our Services</button>
      <button @click="goToContact">Contact Us</button>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router';

cars=
{id:1,Name:"Coupe",Price,torque,Speed,
  id:1,Name:"Mercedes Benz",Price:3000000,torque:2500,Speed:300,
  id:1,Name:"Audi R8",Price:4000000,torque:3000,Speed:400,
  id:1,Name:"Porsche",Price:5000000,torque:3500,Speed:500,
  id:1,Name:"Lamborghini",Price:6000000,torque:4000,Speed:600,
  id:2,Name:"SUV",Price,torque,Speed
  id:2,Name:"Jeep",Price:8000000,torque:6000,Speed:650
};

const router = useRouter();

function goToAbout() {
  router.push({ name: 'About' });
}

function goToServices() {
  router.push({ name: 'Services' });
}

function goToContact() {
  router.push({ name: 'Contact' });
}
</script>

<style scoped>
.home-page {
  text-align: center;
  max-width: 600px;
  margin: 50px auto;
}
h1 {
  font-size: 2.5em;
  color: #333;
}
p {
  font-size: 1.2em;
  margin: 20px 0;
  color: #666;
}
.buttons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 30px;
}
button {
  padding: 10px 20px;
  font-size: 1em;
  color: #fff;
  background-color: #4CAF50;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}
button:hover {
  background-color: #45a049;
}
</style>
