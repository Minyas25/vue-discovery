<script lang="ts" setup>
import { Dog } from 'entities';

const {data, refresh} = useFetch<Dog[]>('http://localhost:8000/api/dog');

async function addDog(dog:Dog) {
    await $fetch('http://localhost:8000/api/dog', {
        method: 'POST',
        body: dog
    });
    refresh();
}
    
</script>


<template>
    <FormDog @submitDog="addDog($event)" />
    <DogItem v-for="item of data" :dog="item" />
</template>