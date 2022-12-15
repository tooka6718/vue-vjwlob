<template>
  <div class="w-1/2 mx-auto">
    <div class="flex flex-col mb-5">
      <Assignments :assignments="inProgressAssignments" title="In Progress" />

      <Assignments :assignments="completedAssignments" title="Completed" />

      <!-- click submit call method add  e.preventdevault -->

      <form class="" @submit.prevent="add">
        <div class="border border-gray-400 text-black">
          <input
            placeholder="New Assignment."
            class="p-2"
            v-model="newAssignment"
          />
          <button type="submit" class="p-2 border-l">Add</button>
        </div>
      </form>

      <!-- <app-button :processing="false">Submit Slot</app-button> -->
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import AppButton from './components/AppButton.vue';
import Assignments from './components/Assignments.vue';
export default {
  name: 'App',

  data() {
    return {
      assignments: [
        { name: 'Finsh project', complete: false, id: 1 },
        { name: 'Read chapter 4', complete: false, id: 2 },
        { name: 'Turn in Homework', complete: false, id: 3 },
      ],

      newAssignment: '',
    };
  },

  components: {
    // HelloWorld,
    'app-button': AppButton,
    Assignments,
  },

  methods: {
    add() {
      this.assignments.push({
        name: this.newAssignment,
        complete: false,
        id: this.assignments.length + 1,
      });

      this.newAssignment = '';
    },
  },

  computed: {
    inProgressAssignments() {
      return this.assignments.filter((assignment) => !assignment.complete);
    },

    completedAssignments() {
      return this.assignments.filter((assignment) => assignment.complete);
    },

    // można i tak ale wtedy w propsie :assignments="filters.inProgress"
    filters() {
      return {
        inProgress: this.assignments.filter(
          (assignment) => !assignment.complete
        ),
        completed: this.assignments.filter((assignment) => assignment.complete),
      };
    },
  },
};
</script>
