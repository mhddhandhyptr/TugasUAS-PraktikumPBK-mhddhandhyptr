<template>
  <div class="task-list">
    <h2>Daftar Tugas</h2>
    <ul>
      <li><a href="https://tugas-prak-pbk.vercel.app/" target="_blank">Tugas-1</a></li>
      <li><a href="https://tugas2prakpbkmhddhandhyptr.netlify.app/" target="_blank">Tugas-2</a></li>
      <li><a href="https://tugas3prakpbo-mhddhandhyptr.netlify.app/" target="_blank">Tugas-3</a></li>
      <li><a href="https://tugas4prakpbkmhddhandhyptr.netlify.app/" target="_blank">Tugas-4</a></li>
      <li><a href="https://tugas5prakpbkdhandhy.netlify.app/" target="_blank">Tugas-5</a></li>
      <li><a href="https://mhddhandhyptr-tugas6prakpbk.netlify.app/" target="_blank">Tugas-6</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TaskList',
};
</script>

<style scoped>
.task-list {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.task-list h2 {
  font-size: 24px;
  color: #333;
  margin-bottom: 15px;
}

.task-list ul {
  list-style-type: none;
  padding: 0;
}

.task-list li {
  margin-bottom: 10px;
}

.task-list a {
  color: #007bff;
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s ease;
}

.task-list a:hover {
  color: #0056b3;
}
</style>
