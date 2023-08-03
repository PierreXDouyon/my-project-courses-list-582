<template>
  <div>
    <div v-for="course in courses" :key="course.id">
      <div>Course Name: {{ course.name }}</div>
      <p>Course ID: {{ course.id }}</p>
      <p>Credits: {{ course.credits }}</p>
      <p>Hours: {{ course.hours }}</p>
      <p>Description: {{ course.description }}</p>
      <p>Teacher: {{ course.teacher }}</p>
      <button v-if="!course.added" @click="addToParent(course.id)">
        Add to Parent
      </button>
      <button v-else @click="removeCourse(course.id)">Remove</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "CourseItem1",
  props: {
    courses: {
      type: Array,
      required: true,
    },
  },
  methods: {
    addToParent(courseId) {
      this.$emit("count-to-parent", courseId);
    },
    removeCourse(courseId) {
      this.$emit("remove-course", courseId);
    },
  },
};
</script>

<style scoped lang="scss">
/* Styles  */
</style>
