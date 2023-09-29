<template>
    <button @click="handleClick">{{ title }}</button>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      onClick: Function,
    },
    methods: {
      handleClick() {
        this.onClick();
      },
    },
  };
  </script>
  