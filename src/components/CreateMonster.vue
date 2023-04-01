<script setup lang="ts">
import { ref } from 'vue';
import { Monster } from '../models/Monster';

    const monster = ref<Monster>({ type: "", mood: "", color: "", name: "" })

    const show = ref(true);
    const createMonster = () => {
        show.value = false;
    }

    const restart = () => {
        show.value = true;
        monster.value.type = "";
        monster.value.mood = "";
        monster.value.color = "";
        monster.value.name = ""; 
    }
</script>
<template>
    <div v-if="show">
    <h2>Create monster</h2>
        <form>
            <input v-model="monster.name" type="text" name="name" placeholder="Mr Sniffles, Bob..">
            <input v-model="monster.type" type="text" name="type" placeholder="Fluffy, sticky..">
            <input v-model="monster.mood" type="text" name="mood" placeholder="Evil, cute..">
            <input v-model="monster.color" type="text" name="color" placeholder="Blue, green..">
            <button type="button" @click="createMonster">Create</button>
        </form>
    </div>
    <div v-else>
        <h2>{{ monster.name }}</h2>
        <p>{{ monster.name }} is {{ monster.color }} and is {{ monster.type }}.</p>
        <p>{{ monster.name }} has a tendency to be bit {{ monster.mood }}.</p> 
        <button type="button" @click="restart">Restart</button>
    </div>
</template>
<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Creepster&display=swap');
     h2 {
        font-family: 'Creepster', cursive;
        font-size: 6rem;
        margin: 0;
        cursor: default;
        text-shadow: -5px 0 black, 0 5px black, 5px 0 black, 0 -5px black;
        color: red;
    }

    form {
        display: flex;
        flex-direction: column;
        align-items: center;
        
    }


</style>