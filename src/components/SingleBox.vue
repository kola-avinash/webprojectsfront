<template>
    <div>
        <div v-for="project in projects" :key="project.id">
            <h1>{{ project.id }}</h1>
            <h1>{{ project.title }}</h1>
            <h1>{{ project.description }}</h1>
        </div>
    </div>
</template>
<script>
export default {
    name: 'SingleBox',
    props: {
        projects: Array
    }
}
</script>
<style scoped>

</style>