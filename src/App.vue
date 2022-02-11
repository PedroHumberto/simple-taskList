<template>
  <div id="task-app" class="container">
    <div class="subcontainer">

      <h1>Task List</h1>

      <input 
      type="text" 
      v-model="item" 
      @keyup.enter="submitTask">

      <div class="addbutton">
        <button @click="submitTask">Add Task</button>
      </div>
      <add-task :tasks="tasks"></add-task>
    </div>
  </div>

</template>

<script>
import AddTask from './components/AddTask.vue'

export default {
  components:{
    'add-task': AddTask
  },
  data() {
    return {
      id: 5,
      item: '',
      tasks: []
    }
  },
  created() {
    fetch('../data/taskList.json')
    .then(res => res.json())
    .then(data => this.tasks = data)
  },
  methods: {
      submitTask(){
         if(this.item != ''){
            this.tasks.push({id: this.id++, item: this.item, status: false})
          }
          this.item = ''
      }
  },
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .container{
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;
    margin: 15px auto;
    height: 500px;
  }
  .subcontainer{
    border: 3px dashed green;
    border-radius: 10px;
    margin: 10px auto;
    width: 400px;
  }
  h1, input{
    display: flex;
    justify-content: center;

    margin: 5px auto;
  }
  .addbutton{
    display: flex;
    justify-content: center;
    margin-bottom: 10px;
  }


</style>
