<template>
  <body>
    <HeaderKanban @saveColumn="addColumn"/>
    <ColumnsKanban :columns="columns" :tasks="tasks" @addTask="addTaskToColumn" @closeModalEvent="closeModalWindow"/>
    <FooterKanban />
  </body>
</template>

<script>
import { defineComponent } from "vue";
import HeaderKanban from "@/components/HeaderKanban.vue";
import FooterKanban from "./components/FooterKanban.vue";
import ColumnsKanban from "./components/ColumnsKanban.vue";
export default defineComponent({
  name: "TheApp",
  components: {
    HeaderKanban, FooterKanban, ColumnsKanban
  },
  data() {
    return {
      viewModal: false,
      columns: [
      {
    id: "to-do",
    title: "Задачи",
    icon: "./src/assets/kanban__column--to-do.svg",
    tasks: []
  },
  {
    id: "in-progress",
    title: "В процессе",
    icon: "./src/assets/kanban__column--in-progress.svg",
    tasks: []
  },
  {
    id: "done",
    title: "Выполнено",
    icon: "./src/assets/kanban__column--done.svg",
    tasks: []
  }],

    tasks: [
    {
    id: 1,
    title: "Задача 1",
    description: "Описание задачи 1",
    dueDate: "16.11.2023",
    columnId: "to-do"
  },
  {
    id: 2,
    title: "Задача 1",
    description: "Описание задачи 1",
    dueDate: "16.11.2023",
    columnId: "to-do"
  }
    ]
    }
  },
  
  methods: {
    closeModalWindow() {
      this.viewModal = false
    },

    addTaskToColumn(newUser) {
      this.users.push(newUser);
      this.closeModalWindow();
    },

    addColumn(data) {
      this.columns.push(data);
    }

  }
});
</script>

<style>
* {
  font-family: "Montserrat", sans-serif;
}
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: #2b1887;
  color: white;
  min-height: 100vh;
  min-width: 380px;
}

html {
  min-width: 380px;
}

.header__container,
footer {
  background-color: #1c0e5e;
  text-align: center;
  padding: 10px 0;
}

.header__title,
.footer__text {
  margin: 0;
  padding: 10px 0;
}

.container {
  width: 100%;
  padding: 0 15px;
  margin: 0 auto;
}

@media screen and (max-width: 768px) {
  .container {
    max-width: 540px;
    margin: 0;
    padding: 0;
  }
}

@media screen and (min-width: 576px) {
  .container {
    max-width: 540px;
  }
}

@media screen and (min-width: 768px) {
  .container {
    max-width: 720px;
  }
}

@media screen and (min-width: 992px) {
  .container {
    max-width: 960px;
  }

  .kanban__column {
    flex: 0 0 calc(33.333% - 20px);
  }
}

@media screen and (max-width: 992px) {
  .kanban {
    width: 100%;
    flex-wrap: wrap;
    flex-direction: column;
    padding: 20px;
  }

  .kanban__column {
    width: 100%;
  }
}

@media screen and (min-width: 1200px) {
  .container {
    max-width: 1140px;
  }
}

@media screen and (min-width: 1400px) {
  .container {
    max-width: 1320px;
  }
}
</style>
