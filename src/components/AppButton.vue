<template>
  <div>
    <button class="bg-gray-400 hover:bg-gray-200 rounded px-5 py-2 mt-5">
      <slot />
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      processing: true,
    };
  },

  props: {},
};
</script>
