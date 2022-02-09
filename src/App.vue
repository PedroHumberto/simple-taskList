<template>
  <div>
    <h1>Task List</h1>
    <input type="text" v-model="item">
    <button @click="submitTask">Add Task</button>
    <add-task :tasks="tasks"></add-task>

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
      item: '',
      tasks: [],
    }
  },
   methods: {
        submitTask(){
            if(this.item != ''){
                this.tasks.push(this.item)
            }
            this.item = ''
        }
    },
}
</script>

<style>

</style>
