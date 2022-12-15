<template>
  <div>
    <button
      :class="{
        'rounded px-5 py-2 mt-5': true,
        'bg-blue-200 hover:bg-blue-400': type === 'primary',
        'bg-purple-200 hover:bg-purple-400': type === 'secondary',
        'bg-gray-200 hover:bg-gray-400': type === 'muted',
        'is-loading': processing,
      }"
      :disabled="processing"
    >
      <slot />
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },

  props: {
    type: {
      type: String,
      default: 'primary',
    },
    processing: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style>
@keyframes spinner {
  to {
    transform: rotate(360deg);
  }
}

.is-loading {
  color: transparent;
}
.is-loading:before {
  content: '';
  box-sizing: border-box;
  position: absolute;
  /* top: 50%; */
  left: 50%;
  width: 20px;
  height: 20px;
  /* margin-top: -10px; */
  margin-left: -10px;
  border-radius: 50%;
  border: 2px solid #ccc;
  border-top-color: #000;
  animation: spinner 0.6s linear infinite;
}
</style>
