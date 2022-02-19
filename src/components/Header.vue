<template>
    <header>
        <h1>{{title}}</h1>
        <AddTask text="Add Task" color="#00ced1	" />

    </header>
    
</template>

<script>
import AddTask from './NewTaskButton.vue'

export default {
    name: 'HeaderItem',
    props: {
        title: {
            type: String,
        }
    },
    components: {
        AddTask,
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>

