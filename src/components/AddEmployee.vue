<template>
  <form class="add-form">
    <h2>Add a New Employee</h2>
    <div class="form-control">
      <label>Full Name</label>
      <input type="text" v-model="Name" name="text" placeholder="Enter your name">
    </div>
    <div class="form-control">
      <label>Designation</label>
      <input type="text" v-model="Designation" name="desig" placeholder="Enter your designation">
    </div>
    <div class="form-control">
      <label>Gender</label>
      <div class="form-control-check">
      <input type="radio" v-model="Gender" id="one" value="male">
      <label for="one">Male</label>
      <input type="radio" v-model="Gender" id="two" value="female">
      <label for="two">Female</label>
      </div>
    </div>

    <button @click.prevent="onSubmit()" class="btn">Add Employee</button>
  </form>
</template>

<script>
export default {
  name: "AddEmployee",
  data(){
    return{
      Name:'',
      Designation: '',
      Gender: ''
    }
  },
  methods:{
    onSubmit() {
      if (!this.Name) {
        alert('Please add an employee!')
        return
      }

      const newEmployee = {
        id: Math.random() * 1000 / Math.random(),
        Name: this.Name,
        Designation: this.Designation,
        Gender: this.Gender,
        Status: true,
      }

      console.log(newEmployee)
      this.$emit('add-em', newEmployee)
      this.Name = ''
      this.Designation= ''
      this.Gender = ''
      this.Status = true
    }
  }
}

</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
label{
  color: #175676;
  font-size: 20px;
  font-family: "Nunito Sans SemiBold";
}
input{
  background-color: rgba(238, 244, 255, 0.65);
  border: none;
  border-radius: 9px;

}
.form-control {
  background: none;
  border: none;
  margin: 20px 0;
  padding-left: 20px;
  padding-right: 50px;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  justify-content: left;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
.btn {
  flex: 3;
  align-items: center;
  background: #ba324f;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin-left: 40%;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:hover{
  color: #fff;
  background: #0e3849;
}
h2{
  margin-left: 25%;
  font-family: "Nunito Sans";
  color: #093042;
}
.btn-block{
  margin-top: 20px;
}
</style>