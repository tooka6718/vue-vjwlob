<template>
  <li>
    <label>
      {{ assignment.name }}
      <input type="checkbox" v-model="assignment.complete" />
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
