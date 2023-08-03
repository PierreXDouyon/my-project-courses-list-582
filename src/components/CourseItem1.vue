<template>
  <div>
    <div v-for="course in courses" :key="course.id">
      <div>Course Name: {{ course.name }}</div>
      <p>Course ID: {{ course.id }}</p>
      <p>Credits: {{ course.credits }}</p>
      <p>Hours: {{ course.hours }}</p>
      <p>Description: {{ course.description }}</p>
      <p>Teacher: {{ course.teacher }}</p>
      <button @click="innerRemove(course.id)">remove</button>
      <button @click="outerAdd">Add to Parent</button>
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
    innerRemove(courseId) {
      this.$emit("remove-course", courseId);
    },
    outerAdd() {
      this.$emit("count-to-parent");
    },
  },
};
</script>

<style lang="scss">
/* Styles if any */
</style>
