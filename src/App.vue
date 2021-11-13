<template>
  <div>
    <Header />
    <div class="split left">
      <div class="container">
        <AddEmployee @add-em="addEm" />
      </div>
    </div>
    <div class="split right">
      <RemoveEmployee v-bind:remployees="remployees"/>
    <Employees @remove-emp="removeEm" v-bind:employees="employees"/>
    </div>
    <div class="foot">
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
import AddEmployee from "@/components/AddEmployee";
import Employees from "@/components/Employees";
import RemoveEmployee from "@/components/RemoveEmployee";
import Footer from "@/components/Footer";
export default {
  name: "App",
  components:{
    Header,
    Employees,
    AddEmployee,
    RemoveEmployee,
    Footer
  },
  data(){
    return{
      employees:[],
      remployees:[]
    }
  },
  methods:{
    addEm(employee){
      console.log(employee);
      this.employees= [...this.employees,employee]
    },
    removeEm(employee){
      if(employee.Status==true) {
        this.remployees = this.remployees.filter((remp) => remp != employee)

      }
      else{
            console.log(this.employees.Status),
            this.remployees = [...this.remployees, employee]
      }
    },
  },
  created() {
    this.employees=[
      {
        id:1,
        Name:'Md. Arif Hasan',
        Designation: 'CEO',
        Gender: 'male',
        Status: true,
      },
      {
        id:2,
        Name:'Jafar Mahin',
        Designation: 'CFO',
        Gender: 'male',
        Status: true,
      },
      {
        id:3,
        Name:'Mustahid Hasan',
        Designation: 'CTO',
        Gender: 'male',
        Status: true,
      }
    ]
    this.remployees=[

    ]
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Nunito', sans-serif;
  background-color: #e19d75;
}
.container {
  background: #CCE6F4;
  justify-content: center;
  margin-left: 30px;
  width: 400px;
  overflow: auto;
  min-height: 300px;
  border: 1px solid #175676;
  padding: 30px 20px 30px 20px;
  border-radius: 5px;
  box-shadow: 0 4px 8px 0 rgba(3, 3, 3, 0.2);
}
.foot{
  z-index: 1;
}
.split{
  height: 100%;
  width: 50%;
  position: absolute;
  z-index: -1;
  top: 90px;
  padding: 20px 30px 30px 10px;
}
.left {
  justify-content: center;
  padding-left: 40px;
  left: 0;
}
.right {
  right: 0;
  display: flex;
  flex-direction: column;
}
.btn {
  display: inline-block;
  background: #175676;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:hover{
  color: #fff;
  background: #5d2a08;
}
.btn-block {
  display: block;
  width: 100%;
}
</style>

