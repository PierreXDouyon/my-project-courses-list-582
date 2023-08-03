<template>
  <div>
    <h1>Course List App</h1>
    <p>{{ count }}</p>
    <CourseItem1
      :courses="courses"
      @remove-course="removeCourse"
      @count-to-parent="addOne"
    />
  </div>
</template>

<script>
import CourseItem1 from "./components/CourseItem1.vue"; // Correct the import statement

export default {
  name: "App",
  data() {
    return {
      courses: [
        {
          id: 1,
          name: "Math",
          credits: 3,
          hours: 45,
          description: "Mathematics course",
          teacher: "John Smith",
        },
        {
          id: 2,
          name: "Science",
          credits: 4,
          hours: 60,
          description: "Science course",
          teacher: "Jane Doe",
        },
        {
          id: 3,
          name: "History",
          credits: 3,
          hours: 40,
          description: "History course",
          teacher: "Michael Johnson",
        },
        // Add more courses here...
      ],
      count: 0,
    };
  },
  components: {
    CourseItem1,
  },
  methods: {
    addOne() {
      this.count++;
    },
    removeCourse(courseId) {
      this.courses = this.courses.filter((course) => course.id !== courseId);
    },
  },
};
</script>

<style lang="scss">
/* Styles if any */
</style>
