<template>
    <div v-if="visible" class="modal">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <h2>Добавить новую задачу</h2>
        <form @submit.prevent="addTask">
          <label for="title">Название:</label>
          <input type="text" v-model="task.title" id="title" required>
          
          <label for="description">Описание:</label>
          <input type="text" v-model="task.description" id="description" required>
          
          <label for="date">Дата:</label>
          <input type="date" v-model="task.date" id="date" required>
          
          <button type="submit">Добавить</button>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "modal-task",
    props: ['visible', 'columnId'],
    data() {
      return {

        }
      },
    methods: {
      
    }
  };
  </script>
  
  <style scoped>
  
  </style>
  