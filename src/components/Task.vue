<template>

</template>
  
<script>
  export default {
    name: "tasks_kanban",
    props: {

},

data() {
return {
    tasks: [
          {
            id: 1,
            title: "Задача 1",
            description: "Описание задачи 1",
            complexity: "high",
            dueDate: "16.11.2023",
            columnId: "to-do"
          },
          {
            id: 2,
            title: "Задача 1",
            description: "Описание задачи 1",
            complexity: "high",
            dueDate: "16.11.2023",
            columnId: "to-do"
          }]}},

methods: {

}};
</script>
  
<style scoped>

</style>