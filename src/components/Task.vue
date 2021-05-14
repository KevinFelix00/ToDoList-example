<template>
    <div v-bind:class="[task.reminder ? 'reminder' : '', 'task']"> 
        <div v-bind:class="{'task.reminder':task.completed}">
   <h3>{{ task.text }}
      
            <input type="checkbox" v-on:change=" markcomplete">
            <button @click="$emit('del-task', task.id)" class="del">x</button>
           <!-- <i @click="onDelete(task.id)" class="fas fa-times"></i> -->
    </h3> 
  
   <p>{{ task.day }}</p> 
        </div>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object,
    },
    methods: {
        markcomplete(completed) {
            console.log(completed)
           this.tasks.completed = !this.tasks.completed;

        }
    }
}
</script>

<style scoped>
.del {
    background-color: red;
    color: #fff;
    border: none;
    padding:5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
.task {
    background-color: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
.task.reminder {
    border-left: 5px solid green;
}
.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>