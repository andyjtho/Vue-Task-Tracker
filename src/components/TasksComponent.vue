<template>
    <div v-for="task in tasks" :key="task.id">
        <task-component @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"/>
    </div>
</template>

<script>
import TaskComponent from './TaskComponent.vue'

export default {
    name: 'TasksComponent',
    props: {
        tasks: Array
    },
    components: {
        TaskComponent,
    },
    emits: ['delete-task', 'toggle-reminder']
}
</script>
