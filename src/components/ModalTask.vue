<template>
    <div class="modal">
        <div class="modalForm">
            <input v-model="taskName" />
            <input v-model="taskDescription" />
            <input type="date" v-model="taskDueDate">
            <button @click="addTask">Сохранить</button>
            <button @click="closeModal">Отмена</button>
        </div>
    </div>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
    name: "ModalTask",
    data() {
        return {
            taskName: null,
            taskDescription: null,
            taskDueDate: null
        }
    },
    methods: {
        addTask() {
            this.$emit('addTask', {title: this.taskName, description: this.taskDescription, dueDate: this.taskDueDate})
            
        },
        closeModal() {
            this.$emit('closeModal')
        },

    },
});
</script>

<style scoped>
    .modal {
  position: fixed;
  top: 0;
  left: 0;

  width: 100%;
  height: 100%;

  background-color: #FFFFFF4F;
  backdrop-filter: blur(2px);

  display: flex;
  align-items: center;
  justify-content: center;

}
.modalForm {
  display: flex;
  flex-direction: column;
}
</style>
