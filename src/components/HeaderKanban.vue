<template>
  <ModalColumn v-if="ModalVisible"
  @closeModalColumn="closeModalColumnkanban"/>
  <header class="header">
    <div class="container header__container">
      <h1 class="header__title">Kanban Board</h1>
      <div class="header__option">
        <img
          @click="openModalAddColumn"
          src="@/assets/add-column-plus.svg"
          alt="header__icon--add"
          class="header__icon--add"
        />
        <div class="header__user-icon">К.П</div>
      </div>
    </div>
  </header>
</template>

<script>
import { defineComponent } from "vue";
import ModalColumn from "./ModalColumn.vue";
export default defineComponent({
  name: "HeaderKanban",
  
  components: {
    ModalColumn
  },

  props: {

  },

  data() {
    return {
      ModalVisible: false
    };
  },

  methods: {
    openModalAddColumn() {
      this.$emit('addColumnEvent');
    },
    openModalAddColumn() {
      this.ModalVisible = true
    },
    closeModalColumnkanban() {
      this.ModalVisible = false
    },
    

  },
});
</script>

<style scoped>
.header {
  margin-top: 10px;
}

.container {
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
}

.header__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px;
}

.header__title {
  font-weight: 300;
}

.header__option {
  display: flex;
  align-items: center;
  gap: 15px;
}

.header__user-icon {
  width: 40px;
  height: 40px;
  background-color: #d9d9d9;
  border-radius: 50%;
  color: #333;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
}

.header__icon--add:hover {
  cursor: pointer;
  opacity: 0.5;
}
</style>
