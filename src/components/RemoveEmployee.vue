<template>
  <div class="rem">
    <div v-bind:key="remployee.id" v-for="remployee in remployees">
    <Rsingle v-bind:remp="remployee" />
    </div>
  </div>
</template>

<script>
import Rsingle from "@/components/Rsingle";

export default {
  name: "RemoveEmployee",
  props:{
    remployees: Array
  },
  components:{
    Rsingle
  }
}
</script>

<style scoped>

</style>