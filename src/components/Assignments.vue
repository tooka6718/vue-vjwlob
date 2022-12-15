<template>
  <div class="flex w-screen flex-col items-center mb-5" >
    <h2 class="font-bold mb-2 border p-4 my-4" v-show="assignments.length">
      {{ title }}
    </h2>
    <ul class="border divide-y divide-gray-400">
      <Assignment 
        v-for="assignment in assignments"
        :key="assignment.id" 
        :assignment="assignment"
      >
        <label class="flex justify-between">
          {{ assignment.name }}
          <input type="checkbox" v-model="assignment.complete" class="ml-5" />
        </label>
      </li>
    </ul>
  </div>
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
