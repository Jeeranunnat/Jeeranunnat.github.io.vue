<template>
  <header><h1>ระบบจัดการข้อมูลพนักงาน</h1></header>
  <FormComponent @save='insertEmployee'></FormComponent>
  <section class="employee-content">
    <h2>ข้อมูลพนักงาน</h2>
    <ListData/>
    <!-- <h1>App Component</h1>
    <FormComponent/>
    <ListData :employees='employees'></ListData> -->
  </section>
</template>

<script>
import ListData from './components/ListData.vue'
import FormComponent from './components/FormComponent.vue'
export default {
  name: 'App',
 components: {ListData, FormComponent},
 data(){
   return {employee:[]}},
 methods:{
   insertEmployee(data){
     console.log('รับข้อมูลพนักงาน = ',data)
     this.employee.puch(data)
   }

 }
//  components: {ListData}
  // data(){
  //   return{
  //     employees:[
  //       {name:'ก้อง', salary:40000},
  //       {name:'แก้ม', salary:30000},
  //       {name:'โจโจ้', salary:20000},
  //       {name:'สมปอง', salary:15000},
  //       {name:'ชาลี'},
  //       {salary:50000}
  //     ]
  //   }
  // }

}


</script>

<style>
*{
  box-sizing: border-box;
}
body{
  margin: 0;
}
header{
  box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.26);
  margin:3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: purple;
  color: #fff;
  text-align: center;
}
.employee-content{
  box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem ;
  padding: 3rem;
  border-radius: 10px;
  text-align: center;
}
.employee-content h2{
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: purple;
  margin: 0 0 1rem 0;
}
</style>