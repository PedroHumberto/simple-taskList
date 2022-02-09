<template>
    <div>
        
        <ul>
            <li v-for="task in tasks" :key="task.id">
                {{ task }}
            </li>
        </ul>
        
    </div>
</template>

<script>
export default {
    props: {
        tasks:{
            required: true,
            type: Array,
            default: []
        }
    }, 
    
    data() {
        return {
        }
    },
   

}
</script>

<style>

</style>