<template>
  <div class="home">
    <FormEmployee title="Create New Employee"/>
    <FormEmployer title="New Employer" class="mt-4"/>
  </div>
</template>

<script>
// @ is an alias to /src
import FormEmployee from "@/components/AddEmployee.vue";
import FormEmployer from "@/components/AddEmployer.vue";

export default {
  name: "Home",
  components: {
    FormEmployee,
    FormEmployer,
  },
};
</script>
