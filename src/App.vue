<template>
  <div class="flex min-h-screen w-screen flex-col items-center">
    <Assignments :assignments="inProgressAssignments" title="In Progress" />
    <Assignments :assignments="completedAssignments" title="Completed" />
    <!-- <app-button :processing="false">Submit Slot</app-button> -->
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
    };
  },

  components: {
    // HelloWorld,
    'app-button': AppButton,
    Assignments,
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
