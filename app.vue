<template>
  <div>
    <p>
      {{ data }}
    </p>
  </div>
</template>

<script setup>
const data = await useFetch('http://localhost:8000/api/message');
console.log(data);
</script>
