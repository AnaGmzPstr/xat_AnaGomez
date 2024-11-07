<!-- Missatge component -->
<script setup>
import { ref } from 'vue';


// Variables
const missatge = ref('');
const emit = defineEmits(['enviar']);


// Función enviar
function enviar() {
    if (missatge.value.trim() !== '') {
        emit('enviar', missatge.value);
        missatge.value = '';
    }
}
</script>


<template>
    <div class="container-text">
        <input 
        type="text" 
        id="xat" 
        v-model="missatge" 
        placeholder="Escriu un missatge" 
        @keyup.enter="enviar"/>
        <button @click="enviar" class="btn-enviar">Enviar</button>
    </div>
</template>


<style>
.container-text {
    display: flex;
    bottom: 0%;
}


#xat {
    width: 100%;
    padding: 10px;
    font-size: 18px;
    border: none;
    border-radius: 8px 0 0 8px;
    background-color: #f0f0f0;
    color: grey;

}

#xat:focus {
    outline: none;
}

.btn-enviar {
    background-color: #4CAF50;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 0px 8px 8px 0px;
    cursor: pointer;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
    transition: ease-in-out .3s;
}

.btn-enviar:hover{
    background-color: #00A884;
}
</style>
