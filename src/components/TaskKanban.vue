<template>
  <div class="task-item" >
    <div class="task-item__title">{{ task.title }}</div>
    <div class="task-item__description">{{ task.description }}</div>
    <div class="task-item__client">{{ task.dueDate }}</div>
    <button>Редактировать</button>
  </div>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "TaskKanban",
  props: {
    task: Object
  },
  data() {
    return {

    }
  },

  methods: {

  },
});
</script>

<style scoped>
.task-item {
    background-color: #f4f2ff;
    border-radius: 10px;
    padding: 10px 20px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%; 
  }
   
  .task-item__info {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  .task-item__complexity {
    display: flex;
    align-items: center;
    margin-right: 15px;
  }
   
  .complexity__dot {
    width: 24px;
    height: 12px;
    flex-shrink: 0;
    background-color: #d9d9d9; 
    border-radius: 0px 10px 10px 24px;
    display: inline-block;
    margin-right: 5px;
  }
   
  .complexity__dot--medium {
    background-color: #FDE047; 
  }

  .complexity__dot--high {
    background-color: #e42c5f; 
  }
  
  .complexity__dot--low {
    background-color: #2ce49d; 
  }

  .complexity__dot--done {
    background-color: #2d41a7; 
  }
  
  .task-item__title {
    flex-grow: 1;
    font-weight: 600;
    color: #333;
  }

  .task-item__description {
    color: gray;
    font-size: 12px;
    margin: 10px 0;
  }
  
  .task-item__client {
    font-size: 14px;
    color: #4F46E5; 
    text-align: center;
  }
</style>
