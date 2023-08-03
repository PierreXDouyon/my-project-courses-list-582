<template>
  <div>
    <h1>Course List App</h1>
    <p>{{ count }}</p>
    <CourseItem1
      :courses="courses"
      @remove-course="removeCourse"
      @count-to-parent="addToParent"
    />
  </div>
</template>

<script>
import CourseItem1 from "./components/CourseItem1.vue";

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
          added: false,
        },
        {
          id: 2,
          name: "Science",
          credits: 4,
          hours: 60,
          description: "Science course",
          teacher: "Jane Doe",
          added: false,
        },
        {
          id: 3,
          name: "History",
          credits: 3,
          hours: 40,
          description: "History course",
          teacher: "Michael Johnson",
          added: false,
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
    addToParent(courseId) {
      const course = this.courses.find((course) => course.id === courseId);
      if (course && !course.added) {
        course.added = true;
        this.count++;
      }
    },
    removeCourse(courseId) {
      const course = this.courses.find((course) => course.id === courseId);
      if (course && course.added) {
        course.added = false;
        this.count--;
      }
    },
  },
};
</script>

<style lang="scss">
/* Styles if any */
</style>
