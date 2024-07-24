<template>
    <footer class="footer">
    <p class="footer__text">To-Do-List-Kanban</p>
  </footer>
  </template>
  
  <script>
import { defineComponent } from 'vue';

  export default defineComponent ({
    name: "FooterKanban",
    props: {

},

data() {
return {

}
},

methods: {

}
});
  </script>
  
  <style scoped>
  .footer {
    background-color: #1C0E5E;
  text-align: center;
  padding: 10px 0;
  }

  .footer-text {
    margin: 0;
  padding: 10px 0;
  }

  </style>