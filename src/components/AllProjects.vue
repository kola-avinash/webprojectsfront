<template>
  <div class="main">
    <h1>ALL Projects</h1>
    <div class="studentproject">
      <table>
        <thead>
          <tr>
            <th>Project Name</th>
            <th>Student Name</th>
            <th>Student ID</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="project in projects" :key="project.id">
            <td>{{ project.title }}</td>
            <td>{{ project.student.name }}</td>
            <td>{{ project.student.student_id }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AllProjects',
  props: {
    projects: Array
  }
}
</script>

<style scoped>
.main {
  font-family: Arial, sans-serif;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  text-align: center;
  font-size: 2.5em;
  margin-bottom: 40px;
}

.studentproject table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

.studentproject th,
.studentproject td {
  padding: 10px;
  text-align: left;
  border: 1px solid #ddd;
}

.studentproject th {
  background-color: #f4f4f4;
  font-weight: bold;
}

.studentproject tr:nth-child(even) {
  background-color: #f9f9f9;
}

.studentproject tr:hover {
  background-color: #f1f1f1;
}

@media screen and (max-width: 768px) {
  .studentproject table {
    font-size: 14px;
  }

  h1 {
    font-size: 2em;
  }
}
</style>
