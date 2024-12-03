<template>
    <div class="main">
      <h1>Students in Class</h1>
      <div class="students">
        <div v-for="project in projects" :key="project.id" class="student-card">
          <h2>{{ project.student.name }}</h2>
          <p><strong>Student ID:</strong> {{ project.student.student_id }}</p>
          <p><strong>Email:</strong> {{ project.student.email }}</p>
        </div>
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
  
  .students {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); /* Auto adjust columns based on screen size */
    gap: 30px;
    padding: 20px;
  }
  
  .student-card {
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding: 20px;
    transition: transform 0.3s ease;
    display: flex;
    flex-direction: column;
    text-align: center;
  }
  
  .student-card:hover {
    transform: translateY(-10px);
  }
  
  .student-card h2 {
    font-size: 1.8em;
    color: #1a73e8;
    margin-bottom: 15px;
  }
  
  .student-card p {
    font-size: 1em;
    line-height: 1.6;
    margin: 5px 0;
  }
  
  .student-card p strong {
    font-weight: bold;
  }
  
  @media screen and (max-width: 768px) {
    .container {
      padding: 10px;
    }
  
    h1 {
      font-size: 2em;
    }
  }
  </style>
  