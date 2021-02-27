<template>
  <div>
    {{ msg }}
    <form id="form">
      <button>Todoを増やす</button>
      <button>Todoを消す</button>
      <p>input: <input type="text" name="title" /></p>
      <p>task:</p>
    </form>
    <div class="task-list">
      <label class="item" v-for="todo in todos" v-bind:key="todo.id">
        <input type="checkbox" /><button>EDIT</button> {{ todo.text }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "todo",
  data() {
    return {
      msg: "Message Todo",
      todos: [
        { id: 1, text: "vue-router", done: false },
        { id: 2, text: "vuex", done: false },
        { id: 3, text: "vue-loader", done: false },
        { id: 4, text: "awesome-vue", done: true },
      ],
    };
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
