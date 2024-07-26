<template>
   <div class="kanban container">
      <div class="kanban__column">
        <div class="kanban__header">
          <div class="kanban__header-content">
          asd
          </div>
          <img src="./src/assets/add-column-plus.svg" alt="Plus">
        </div>
      </div>
   </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ColumnsKanban',
  props: {
    type: Object,
    required: true,
  }
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

.kanban__column {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 24px;
  flex: 1 0 0;

  padding: 14px;

  border-radius: 12px;
  background-color: #D5CCFF;
}

.container {
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
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
  color: #2B1887;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.kanban__icon--add {
  color: #2B1887;
}

.kanban__icon--add:hover {
  cursor: pointer;
  opacity: .5;
}

.kanban__list {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 100%;
}
</style>