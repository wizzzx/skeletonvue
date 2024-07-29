<template>
    <div class="modal">
        <div class="modalForm">
            <input v-model="columnId"/>
            <input v-model="columnTitle"/>
            <button @click="saveColumn">Сохранить</button>
            <button @click="isModalVisible">Отмена</button>
        </div>
    </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "ModalColumn",
  props: {

  },

  data() {
    return {
      columnId: null,
      columnTitle: null,
    };
  },

  methods: {
    isModalVisible() {
      this.$emit('closeModalColumn')
    },
    saveColumn() {
      this.$emit('saveColumn', {id: this.columnId, title: this.columnTitle})
    }
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
