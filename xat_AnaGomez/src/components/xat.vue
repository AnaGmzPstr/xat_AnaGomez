<!-- Xat component -->
<script setup>
import { reactive } from 'vue';
import Missatge from './missatge.vue';


// Array reactivo para almacenar los mensajes
const arrayMissatges = reactive([]);


// Función que recibe el mensaje enviado desde el componente Missatge
const misstageRebut = (rebut) => {
    if (rebut) {
        arrayMissatges.push(rebut);
    }
};


</script>


<template>
    <h3 class="persona">Grup DAWe 2024-2025</h3>
    <div class="container-xat">
        <p class="info-xat" v-if="arrayMissatges.length === 0">No hi han missatges</p>
        <ul v-else>
            <li class="missatge-enviat" v-for="(missatge, index) in arrayMissatges" :key="index"><span>User </span> {{
            missatge }}</li>
        </ul>
        <!-- Componente para enviar nuevos mensajes -->
    </div>
    <Missatge @enviar="misstageRebut" />
</template>
<style>
/* Estilos para el componente */
.container-xat {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    flex: 1;
    height:416px;
    overflow-y: auto;
}


.persona {
    background-color: #075E54;
    color: #F7F7F7;
    padding: 10px;
    border-radius: 10px 10px 0 0;
    margin: 0px;
}


.info-xat {
    font-size: 20px;
    font-weight: bold;
    color: #2A3942;
    align-self: center;
}


.missatge-enviat {
    list-style: none;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    background-color: #1F2C34;
    padding: 10px;
    border-radius: 10px;
    margin: 10px;
    color: #fff;
    max-width: fit-content;
    margin-left: auto;

}

span {
    font-weight: bold;
    color: rgb(232, 138, 210);
}
</style>
