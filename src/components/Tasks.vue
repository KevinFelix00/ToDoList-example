<template>
    <div>
        <div v-bind:key="task.id" v-for="task in tasks">
            <h3>{{ task.text }}</h3>
            <p>{{ task.day }}</p> 
            <Task :task="tasks" v-on:del-task="$emit('del-task', task.id)"/>
        </div>
        
   </div>   
</template>

<script>
import Task from './Task'

export default {
    name: 'Tasks',
    props: {
        tasks:Array,
    },
    components: {
        Task,
    }
}
</script>