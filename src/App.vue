<template>
  <div>  
    <ProjectBox :projects="projects" />
    <SingleBox :projects="projects" />
  </div>
</template>

<script>
import ProjectBox from './components/ProjectBox.vue'
import SingleBox from './components/SingleBox.vue'

export default {
  name: 'App',
  components: {
    ProjectBox,
    SingleBox
  },
  data() {
    return {
      projects:[]
    }
  },
  methods: {
   async getProjects() {
    const response = await fetch('https://webprojectsback.onrender.com/api')
    // const response = await fetch('http://localhost:5959/api')
    const data = await response.json()
    return data
   }
  },
  async created() {
    this.projects = await this.getProjects()
    console.log(this.projects)
    
  }
}
</script>

<style>

</style>
