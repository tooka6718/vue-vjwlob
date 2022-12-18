<template>
  <form class="" @submit.prevent="add">
    <div class="border border-gray-400 text-black flex justify-between">
      <input
        placeholder="New Assignment."
        class="p-2"
        v-model="newAssignment"
      />
      <button type="submit" class="border-l p-2 bg-gray-400 w-full">Add</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newAssignment: '',
    };
  },

  props: {},

  methods: {
    add() {
      this.$emit('add', this.newAssignment);
      this.newAssignment = '';
    },
  },
};
</script>
