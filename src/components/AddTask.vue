<template>
    <div>
        <input type="text" v-model="item">
        <button @click="submitTask">Add Task</button>
        <ul>
            <li v-for="task in tasks" :key="task.id">
                {{ task }}
            </li>
        </ul>
        
    </div>
</template>

<script>
export default {
    
    
    data() {
        return {
            tasks: [],
            item: ''
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