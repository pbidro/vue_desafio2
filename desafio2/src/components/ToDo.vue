<template>
  <div class="container">
    <h1>Crea una nueva tarea</h1>
    <div>
      <fieldset>
        <label for="task">Tarea</label>
        <input type="text" name="task" v-model="task" @keydown.enter="insert" />
        <button @click="insert">Crear</button>
      </fieldset>
    </div>
    <div>
      <h2>Lista</h2>
      <ul class="tasks">
        <li v-for="(item, index) in list" :key="index">
          {{ index + 1 }}: {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      task: "",
      list: [],
    };
  },
  methods: {
    insert() {
      this.list.push(this.task);
      this.task = "";
    },
  },
};
</script>

<style scoped>
.container {
  width: 100%;
  max-width: 400px;
  margin: 1em auto;
  font-family: sans-serif;
}
label {
  font-weight: 800;
  margin-right: 0.3em;
}
button {
  margin-left: 0.3em;
}
h1 {
  color: #666;
  text-align: center;
}
h2 {
  color: #666;
  text-align: center;
}
ul {
  max-width: 250px;
  margin: 0 auto;
}
li {
  font-weight: 700;
}
fieldset {
  border: 0;
  width: 70%;
  display: flex;
  margin: auto;
  justify-content: space-around;
}
</style>