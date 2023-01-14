<template>
  <div>
    <p>
      {{ data }}
    </p>
  </div>
</template>

<script setup>
const data = await useFetch('http://localhost:8000/api');
console.log(data);
</script>
