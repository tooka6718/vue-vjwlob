<template>
  
    <form class="" @submit.prevent="add">
      <div class="border border-gray-400 text-black">
        <input
          placeholder="New Assignment."
          class="p-2"
          v-model="newAssignment"
        />
        <button type="submit" class="p-2 border-l">Add</button>
    
    </form>
  </divide>
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
    
    add(){

      this.$emit('add', this.newAssignment);
      this.newAssignment= '';

    },


  },
};
</script>
