<template>
  <div>
    {{ msg }}
    <form id="form">
      <button type="button" v-on:click="addTask()">タスクを増やす</button>
      <button type="button" v-on:click="removeTask()">
        完了したタスクを消す
      </button>
      <p>input: <input type="text" v-model="newTask" /></p>
      <p>task: {{ newTask }}</p>
    </form>
    <div class="task-list">
      <label
        class="item"
        v-for="task in tasks"
        v-bind:key="task.id"
        v-bind:class="{ 'item--checked': task.done }"
      >
        <input type="checkbox" v-model="task.done" /><button>EDIT</button>
        {{ task.text }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "task",
  data() {
    return {
      msg: "Message task",
      tasks: [
        { id: 1, text: "vue-router", done: false },
        { id: 2, text: "vuex", done: false },
        { id: 3, text: "vue-loader", done: false },
        { id: 4, text: "awesome-vue", done: true },
      ],
      newTask: "",
      maxId: 4,
    };
  },
  methods: {
    addTask: function () {
      let text = this.newTask;
      text = text.trim();
      if (!text) {
        return;
      }
      let id = this.maxId + 1;
      this.tasks.push({
        id: id,
        text: text,
        done: false,
      });
      this.newTask = "";
      this.maxId = id;
    },
    removeTask: function () {
      for (let i = this.tasks.length - 1; i > 0; i--) {
        if (this.tasks[i].done) {
          this.tasks.splice(i, 1);
        }
      }
    },
  },
};
</script>

<style scoped>
.task-list {
  display: flex;
  display: -webkit-flex;
  display: -moz-flex;
  display: -ms-flex;
  display: -o-flex;
  flex-direction: column;
  align-items: center;
}
.item {
  width: 270px;
  text-align: left;
}
.item--checked {
  color: #85a6c6;
}
</style>
