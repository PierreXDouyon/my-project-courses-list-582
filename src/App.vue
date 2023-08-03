<template>
  <div>
    <h1>Course List App</h1>
    <p>{{ count }}</p>
    <CourseItem1
      v-for="student in students"
      :key="student.id"
      :given="student"
    />
  </div>
</template>

<script>
import CourseItem1 from "./components/CourseItem1.vue";

export default {
  name: "App",
  data() {
    return {
      students: [
        { id: 1, name: "patrick", credits: 22 },
        { id: 2, name: "john", age: 45 },
        { id: 3, name: "mary", age: 77 },
      ],
      count: 0,
    };
  },
  components: {
    CourseItem1,
  },
};
</script>

<style lang="scss">
/* Styles if any */
</style>
