<template>
  <div class="flex min-h-screen w-screen flex-col justify-center items-center">
    <h2 class="font-bold mb-2 border p-4">Assignments</h2>
    <ul class="border p-4">
      <li v-for="assignment in assignments">
        <label class="flex justify-between">
          {{ assignment.name }}
          <input type="checkbox" v-model="assignment.complete" class="ml-5" />
        </label>
      </li>
    </ul>
    <pre>
      {{ assignments }}
    </pre>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
export default {
  name: 'App',

  data() {
    return {
      assignments: [
        { name: 'Finsh project', complete: false, id: 1 },
        { name: 'Read chapter 4', complete: false, id: 2 },
      ],
    };
  },

  components: {
    // HelloWorld,
  },
};
</script>
