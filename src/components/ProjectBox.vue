<template>
  <div class="main">
    <h1>Web Database Application Projects</h1>
    <div class="projects">
      <div v-for="project in projects" :key="project.id" class="project">
        <h2>{{ project.title }}</h2>
        <p><strong>Description:</strong> {{ project.description }}</p>
        <p><strong>Technologies:</strong> {{ project.technologies && Array.isArray(project.technologies) ? project.technologies.join(', ') : 'N/A' }}</p>
        <p><strong>Student name:</strong>{{ project.student.name }}</p>
        <p><strong>Status:</strong> {{ project.status }}</p>
        <p><strong>Grade:</strong> {{ project.grade || 'N/A' }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectBox',
  props: {
    projects: Array
  }
}
</script>

<style scoped>
.main {
  font-family: 'Arial', sans-serif;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  text-align: center;
  color: #333;
  font-size: 2.5em;
  margin-bottom: 40px;
}

/* Enhanced Grid Layout for projects */
.projects {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); /* Auto adjust columns based on screen size */
  gap: 30px;
  padding: 20px;
}

.project {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  padding: 20px;
  transition: transform 0.3s ease;
  display: flex;
  flex-direction: column;
}

.project:hover {
  transform: translateY(-10px);
}

.project h2 {
  font-size: 1.8em;
  color: #1a73e8;
  margin-bottom: 15px;
}

.project p {
  font-size: 1em;
  line-height: 1.6;
  margin: 5px 0;
}

.project p strong {
  font-weight: bold;
}

.project p:last-child {
  font-weight: bold;
  color: #4caf50;
}

/* Mobile responsiveness (when screen width is less than 768px) */
@media screen and (max-width: 768px) {
  .container {
    padding: 10px;
  }

  h1 {
    font-size: 2em;
  }
}
</style>
