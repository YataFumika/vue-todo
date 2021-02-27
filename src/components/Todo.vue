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
      <label class="item">
        <input type="checkbox" /><button>EDIT</button>vue-router
      </label>
      <label class="item">
        <input type="checkbox" /><button>EDIT</button>vuex
      </label>
      <label class="item">
        <input type="checkbox" /><button>EDIT</button>vue-loader
      </label>
      <label class="item item--checked">
        <input type="checkbox" checked /><button>EDIT</button>awesome-vue
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
