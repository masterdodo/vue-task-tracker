<template>
    <header>
        <h1>{{title}}</h1>
        <Button v-show="homePage" @button-click="$emit('add-task-click')" :text="showAddTask ? 'Close Task Form' : 'Show Task Form'" :color="showAddTask ? 'red' : 'green'" />
    </header>
</template>

<script>
import Button from './Button.vue';
export default {
    name: "Header",
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: { Button },
    computed: {
        homePage() {
            if (this.$route.path === '/') {
                return true
            }
            else {
                return false
            }
        }
    }
}
</script>

<style>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>