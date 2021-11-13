<template>
  <div>
    <div v-bind:key="employee.id" v-for="employee in employees">
      <Employee @remove-emp="$emit('remove-emp',employee)" :text="employee.Status ? 'Remove': 'Keep'" :color="employee.Status ? '#d62839': '#175676'" v-bind:employee="employee" />
    </div>
  </div>
</template>

<script>
import Employee from "@/components/Employee";
export default {
  name: "Employees",
  props:{
    employees: Array,
  },
  components:{
    Employee
  },
  emits:['remove-emp']
}
</script>

<style scoped>

</style>