<template>
  <h2 class="font-bold mb-2 border p-3 my-4" v-show="assignments.length">
    {{ title }}
    <span class="text-red-500">({{assignments.length}})</span>
  </h2>
  <ul class="border divide-y divide-gray-400 mb-2">
    <Assignment
      v-for="assignment in assignments"
      :key="assignment.id"
      :assignment="assignment"
    >

  </ul>
</template>

<script>
import Assignment from './Assignment.vue';
export default {
  data() {
    return {};
  },

  components: {
    Assignment,
  },

  props: {
    assignments: Array,
    title: String,
  },
};
</script>
