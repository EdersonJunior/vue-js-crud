<template>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <strong>Nome:</strong> {{ item.name }}<br>
        <strong>Gênero:</strong> {{ item.gender }}
      </li>
    </ul>
  </template>
  
  <script>
  export default {
    props: {
      items: Array,
    },
  };
  </script>
  