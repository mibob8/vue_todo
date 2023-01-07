<template>
    <div :key="task.id" v-for="task in tasks">
        <TaskComponent @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"></TaskComponent>
    </div>
  
</template>

<script>

import TaskComponent from './Task'


export default {
        name: 'TasksComponent',
        emits: ['delete-task', 'toggle-reminder'],
        components:{
            TaskComponent,
        },
        props: {
            tasks: Array,
        }
}
</script>

<style>

</style>