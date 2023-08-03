<template>
  <div>
    <div>Course Name: {{ given.name }}</div>
    <p>Course ID: {{ given.id }}</p>
    <p>Credits: {{ given.credits }}</p>
    <button @click="innerRemove">remove</button>
    <button @click="outerAdd">Add to Parent</button>
  </div>
</template>

<script>
export default {
  name: "CourseItem1",
  props: {
    given: {
      type: Object,
      required: true,
    },
  },
  methods: {
    innerRemove() {
      // Logic to handle removing a course, if needed.
      // For now, this method is commented out to avoid confusion with the original code.
      // this.$emit("remove-course");
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
