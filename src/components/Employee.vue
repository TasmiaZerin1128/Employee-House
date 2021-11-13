<template>
  <div class="employee">
    <div v-if="employee.Gender=='male'">
      <i class="fas fa-male fa-2x"></i>
    </div>
    <div v-else>
      <i class="fas fa-female fa-2x"></i>
    </div>
    <div class="ND">
      <h5> {{employee.Name}}</h5>
      <p>{{employee.Designation}}</p>
    </div>
    <button @click="onDelete(employee)" v-bind:style="{background:color}" class="btn">{{text}}</button>
  </div>
</template>

<script>
export default {
  name: "Employee",
  props:{
    employee: Object,
    text: String,
    color: String,
  },
  methods:{
    onDelete(emp){
      console.log("Hi from employee",emp);
      emp.Status =! emp.Status,
      this.$emit('remove-emp',emp)
    }
  }
}
</script>

<style scoped>
.fas{
  color: #ffffff;
  padding: 5px 20px 10px 5px;
}
.employee {
  display: flex;
  flex-direction: row;
  align-items: center;
  background: #4ba3c3;
  border-radius: 15px;
  margin-top: 10px;
  margin-left: 20px;
  margin-right: 20px;
  padding: 15px 25px 5px;
  cursor: pointer;
  justify-content: space-between;
}
.btn:hover{
  color: #fff;
  background: #411d06;
}
.ND{
  flex-direction: row;
}

.employee h5 {
  font-family: "Bebas Neue";
  letter-spacing: 1px;
  display: flex;
  align-items: center;
}
p{
  font-size: 14px;
}
.btn {
  width: 100px;
  height: 45px;
  align-items: center;
  background: #8C4009;
  color: #fff;
  border: none;
  padding: 10px 25px;
  margin-left: 40%;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
</style>