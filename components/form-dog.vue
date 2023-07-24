<script lang="ts" setup>
import { Dog } from "../entities";
//const emit = defineEmits(['submitDog'])
const emit = defineEmits<{
  (e: 'submitDog', dog: Dog): void
}>();

const dog = ref<Dog>({
  name:'',
  breed:'',
  birthdate: ''
});

function handleSubmit() {
  emit('submitDog', dog.value)
}

</script>

<template>
  <form @submit.prevent="handleSubmit()">
    <label for="name">Name</label>
    <input type="text" id="name" v-model="dog.name">
    <label for="breed">Breed</label>
    <input type="text" id="breed" v-model="dog.breed">
    <label for="birthdate">Birthdate</label>
    <input type="date" id="birthdate" v-model="dog.birthdate">
    <button>Submit</button>
  </form>
</template>

<style scoped></style>
