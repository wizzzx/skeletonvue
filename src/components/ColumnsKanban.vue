<template>
  <ModalTask v-if="viewModal" 
    @closeModal="closeModalCreateTask"
  />
  <div class="kanban container">
    <div class="kanban__column" v-for="column in columns" :key="column.id">
      <div class="kanban__header">
        <div class="kanban__header-content">
          <img :src="column.icon" />
          <div class="kanban__title">{{ column.title }}</div>
        </div>
        <img
          @click="openModalCreateTask"
          src="@/assets/add-column-plus.svg"
          alt="plus icon"
          class="kanban__icon--add"
        />
      </div>
      <TaskKanban v-for="task in filteredTasks(column.id)" :key="task.id" :task="task" />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import ModalTask from "./ModalTask.vue";
import TaskKanban from "./TaskKanban.vue";
export default defineComponent({
  name: "ColumnsKanban",
  data() {
    return {
      viewModal: false
    }
  },

  components: {
    ModalTask, TaskKanban
  },

  props: {
    columns: {
      type: Array,
      required: true,
    },
    tasks: {
      type: Array,
      required: true,
    }
  },

  methods: {
    openModalCreateTask() {
      this.viewModal = true;
    },
    closeModalCreateTask() {
      this.viewModal = false;
      this.$emit('closeModalEvent', this.viewModal)
    },
    filteredTasks(columnId) {
      return this.tasks.filter(task => task.columnId === columnId);
    },

  },
});
</script>

<style scoped>
.kanban {
  display: flex;
  padding: 40px;
  align-items: flex-start;
  gap: 40px;
  margin: 10px 0;
}

.container {
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
}

.kanban__column {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 24px;
  flex: 1 0 0;
  padding: 14px;
  border-radius: 12px;
  background-color: #d5ccff;
}

.kanban__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
}

.kanban__header-content {
  display: flex;
  align-items: center;
  gap: 10px;
}

.kanban__title {
  color: #2b1887;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.kanban__icon--add {
  color: #2b1887;
}

.kanban__icon--add:hover {
  cursor: pointer;
  opacity: 0.5;
}

.kanban__list {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 100%;
}
</style>
