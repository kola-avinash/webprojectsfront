<template>
  <div>  
    <ProjectBox :projects="projects" />
  </div>
</template>

<script>
import ProjectBox from './components/ProjectBox.vue'

export default {
  name: 'App',
  components: {
    ProjectBox
  },
  data() {
    return {
      projects:[]
    }
  },
  methods: {
   async getProjects() {
    const response = await fetch('https://webprojectsback.onrender.com/api')
    const data = await response.json()
    return data
   }
  },
  async created() {
    this.projects = await this.getProjects()
  }
}
</script>

<style>

</style>
