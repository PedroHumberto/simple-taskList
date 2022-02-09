<template>
  <div>
    <h1>Task List</h1>
    <add-task></add-task>

  </div>

</template>

<script>
import AddTask from './components/AddTask.vue'


export default {
  components:{
    'add-task': AddTask
  }

}
</script>

<style>

</style>
