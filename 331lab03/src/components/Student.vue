<template>
  <div class="event-card">
    <h3>{{ student.name }} {{ student.surname }}</h3>
    <h4>GPA: {{ student.gpa }} PenAmount: {{ student.penAmount }}</h4>
    <h4>{{ student.description }}</h4>
    <img :src="student.image" class="image" />
  </div>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    student: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba (0, 0, 0, 0.2);
}

.image {
  width: 200px;
  height: 200px;
}
</style>
