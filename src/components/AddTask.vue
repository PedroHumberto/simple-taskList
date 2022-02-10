<template>
    <div>
        <div class="card">
            <ul>
                <li v-for="task in tasks" :key="task.id">
                    <div v-if="task.status == false">
                        <button @click="check(task)">Done</button>
                        {{ task.item }}
                        
                    </div>
                    <div v-else style="text-decoration: line-through">
                        <button @click="open(task)">Open</button>
                        {{ task.item }}
                        
                    </div>
                </li>
            </ul>       
        </div>
    </div>
</template>

<script>
export default {
    props: {
        tasks:{
            required: true,
            type: Array | Object,
        }
    },     
    methods: {
        check(task){
            task.status = true
        },
        open(task){
            task.status = false
        }
    }
}
</script>

<style scoped>
    .card{
        border: 2px solid rgb(130, 190, 247);
        border-radius: 10px;
        background-color: rgb(253, 239, 221);
        margin: 10px;
    }
    li{
        display: flex;
        margin: 4px auto;
    }
    button{
        margin-left: 5px;
    }
</style>>

</style>