<template>
  <div class="">
    <input type="text" :value="name" @input="name = $event.target.value" />
    <br />
    <p>{{ name }}</p>
    <div>{{ msg }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'test',
    };
  },

  props: {
    msg: String,
  },
};
</script>
