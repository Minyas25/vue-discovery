<script lang="ts" setup>
const first = ref('test');

function changeFirst() {
  first.value = 'autre chose';
}

</script>

<template>
  <div>
    {{ first }}
  </div>
  <button @click="changeFirst()">Click !</button>
</template>

<style scoped></style>
