<template>
  <header class="header">To Do List</header>
  <div class="container">
    <div class="card">
      <div class="inputcontainer">
        <label for="taskName">Enter the task name </label><br />
        <input type="text" id="taskName" placeholder="Check something" v-model="taskName">
        <button class="addButton" @click="addToList"> + </button>
      </div>
      <div v-if="taskList.length > 0" class="list-container">
        <div v-for="task in taskList" :key="task">
          <div class="checkboxcontainer">
            <label for="task">{{task}}</label>
            <input id="task" class="checkmark" type="checkbox" checked="checked">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>

.header {
  display: flex;
  width: 100%;
  justify-content: center;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.container {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
}

.card {
  margin-top: 10px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 60%;
  padding: 10px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.inputcontainer {
  padding: 2px 16px;
}

.list-container {
  border-radius: 50px;
  margin-top: 20px;
  cursor: pointer;
  padding: 20px;
}

.checkboxcontainer {
  display: block;
  position: relative;
  padding-left: 35px;
  margin-bottom: 12px;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.1);
}

/* Create a custom checkbox */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: #eee;
}

/* On mouse-over, add a grey background color */
.checkboxcontainer:hover input~.checkmark {
  background-color: #ccc;
}

/* When the checkbox is checked, add a blue background */
.checkboxcontainer input:checked~.checkmark {
  background-color: #2196F3;
}

/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the checkmark when checked */
.checkboxcontainer input:checked~.checkmark:after {
  display: block;
}

/* Style the checkmark/indicator */
.checkboxcontainer .checkmark:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
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
