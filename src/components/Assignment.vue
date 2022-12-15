<template>
  <li class="p-3">
    <label class="flex justify-between items-center">
      {{ assignment.name }}
      <input type="checkbox" v-model="assignment.complete" class="ml-3" />
    </label>
  </li>
</template>

<script>
export default {
  data() {
    return {};
  },

  props: {
    assignment: Object,
  },
};
</script>
