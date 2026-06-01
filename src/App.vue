<template>
  <main class="container">
    <h1>🐾 Elige tu Mascota Ideal</h1>

    <section class="card-mascota">
      <img
        :src="mascota.foto"
        :alt="'Foto de ' + mascota.nombre"
        class="imagen-mascota"
      />

      <div class="contenido">
        <h2>{{ mascota.nombre }}</h2>

        <p><strong>Tipo:</strong> {{ mascota.tipo }}</p>
        <p><strong>Edad:</strong> {{ mascota.edad }} años</p>

        <p v-if="mascota.vacunado" class="vacunado">✅ Mascota vacunada</p>

        <p v-else class="no-vacunado">❌ Mascota no vacunada</p>

        <h3>Características</h3>

        <ul>
          <li
            v-for="(caracteristica, index) in mascota.caracteristicas"
            :key="index"
          >
            {{ caracteristica }}
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<script setup>
const mascota = {
  nombre: 'Yack',
  tipo: 'Perro',
  edad: 11,
  vacunado: true,
  foto: '/img/perro.jpg',
  caracteristicas: ['Inteligente', 'Protector', 'Juguetón']
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  padding: 40px 20px;
  text-align: center;
  background-color: #f4f6f8;
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  color: #333;
  margin-bottom: 30px;
}

.card-mascota {
  max-width: 420px;
  margin: 0 auto;
  background-color: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.imagen-mascota {
  width: 100%;
  height: 250px;
  object-fit: cover;
}

.contenido {
  padding: 20px;
}

h2 {
  color: #6a3dc4;
}

.vacunado {
  color: green;
  font-weight: bold;
}

.no-vacunado {
  color: red;
  font-weight: bold;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  background-color: #eee;
  margin: 8px 0;
  padding: 10px;
  border-radius: 8px;
}
</style>
