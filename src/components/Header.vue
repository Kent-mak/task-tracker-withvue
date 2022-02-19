<template>
    <header>
        <h1>{{title}}</h1>
        <ButtonItem text="Add Tasks" color="#00ced1	" />

    </header>
    
</template>

<script>
import ButtonItem from './Button.vue'

export default {
    name: 'HeaderItem',
    props: {
        title: {
            type: String,
        }
    },
    components: {
        ButtonItem,
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

