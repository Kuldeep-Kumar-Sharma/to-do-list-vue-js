<template>
  <header>To Do List</header>
  <div class="card">
    <div class="container">
      <label for="taskName">Enter the task name </label><br />
      <input type="text" id="taskName" placeholder="Check something" v-model="taskName">

      <button class="addButton" @click="addToList"> + </button>

      <ul>
        <li v-for="task in taskList" :key="task">
          {{task}}
        </li>
      </ul>
    </div>
  </div>
  {{taskName}}
</template>

<style>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 60%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
  padding: 2px 16px;
}

input[type=text] {
  width: 80%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  border: none;
  border-bottom: 2px solid red;
}

.addButton {
  background-color: #4CAF50;
  /* Green */
  border: none;
  color: white;
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
  background-color: white;
  color: black;
  border: 2px solid #4CAF50;
}

.addButton:hover {
  background-color: #4CAF50;
  color: white;
}
</style>
<script>
export default {
  name: 'to-do-list',
  data() {
    return {
      taskList:[],
      taskName: ''
    }
  },
  props: {
  },
  methods: {
    addToList: function() {
      this.taskList.push(this.taskName);
      this.taskName = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  color: white;
  padding: 20px;
  background-color: black;
}

</style>
