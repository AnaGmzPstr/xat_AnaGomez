<script setup>
import Xat from './components/xat.vue';


</script>


<template>
  <div class="container">
    <h2>Xat entre usuaris</h2>
    <div class="pantalla">
      <Xat />
    </div>
  </div>
</template>


<style scoped>
.container {
  width: 400px;
  height: 600px;
  margin: 0 auto;
  padding: 0 20px 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

h2 {
  text-align: center;
}

.pantalla {
  flex: 1;
  border: 1px solid #ccc;
  border-radius: 10px;
  background-color: #128C7E;
  max-height:500px;
}
</style>