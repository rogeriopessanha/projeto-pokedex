<script setup>
import { ref } from 'vue';

let num = ref(0)

</script>

<template>
  <div>
<button @click="num++">
  {{ num }}
</button>
  </div>
</template>