<script setup lang="ts">
const names = ref(['Jon', 'Riri', 'Maxou', 'Robert']);

const newName = ref('');

function addName(){
    names.value.push(newName.value);
}

</script>

<template>
    <input type="text" v-model="newName" placeholder="Type a name...">
    <button @click="addName()">Add</button>
    <ul>
        <li v-for="item of names">{{ item }}</li>
    </ul>
</template>
