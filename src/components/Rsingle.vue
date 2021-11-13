<template>
  <div class="column">
    <div class="card">
      <i class="fab fa-ello fa-2x"></i>
      <h5> {{remp.Name}}</h5>
      <p>{{remp.Designation}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Rsingle",
  props:{
    remp: Object
  },
}
</script>

<style scoped>
.column {
  float: left;
  width: 25%;
  padding: 0 10px;
  margin-bottom: 15px;
}
.fab{
  color: #f8cdd6;
  padding-top: 15px;
  padding-bottom: 10px;
}
.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 145px;
  width: auto;
  box-shadow: 0 4px 8px 0 rgba(3, 3, 3, 0.2); /* this adds the "card" effect */
  padding: 16px;
  text-align: center;
  color: white;
  background-color: #ba324f;
}
</style>