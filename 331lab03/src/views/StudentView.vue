<template>
  <h1>Events for Good</h1>
  <div class="events">
    <Student v-for="student in students" :key="student.id" :student="student" />
  </div>
</template>

<script>
// @ is an alias to /src
import Student from '@/components/Student.vue'
import StudentService from '/Users/jeongmin/Desktop/compobased/331lab03/331lab03/services/StudentService.js'
export default {
  name: 'StudentView',
  components: {
    Student
  },
  data() {
    return {
      students: null
    }
  },
  created() {
    StudentService.getEvents()
      .then((response) => {
        this.students = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>
<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.category {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: right;
}
</style>
