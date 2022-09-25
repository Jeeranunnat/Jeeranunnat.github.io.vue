<template>
  <ul>  
        <!-- <Card>พนักงานคนที่ 1</Card>
        <Card>พนักงานคนที่ 2</Card>
        <Card>พนักงานคนที่ 3</Card> -->
        <Person 
            v-for="item in employees" :key='item.id' 
            :id='item.id'
            :name='item.name'
            :salary="item.salary"
            :department='item.department'
            :isVisible='item.isVisible'
            @show="toggleVisible"
            @delete="removeEmployee"
        />
        <!-- <Person/> -->
        
  </ul>
</template>

<script>
import Person from './Person.vue'
// import Card from './Card.vue'
export default {
    name: 'ListData',
    components: {Person},
    data(){
        return {
            // message:'แสดงรายชื่อพนักงาน',
            employees:[
                        {id:1, name:'ชาบู ชูชิ', salary:40000, department:'โปรแกรมเมอร์', isVisible:false},
                        {id:2, name:'โรตี กล้วยไข่', salary:30000, department:'ฝ่ายการตลาด', isVisible:false},
                        {id:3, name:'ชานม ไข่มุก', salary:20000, department:'โปรแกรมเมอร์', isVisible:false},
                        {id:4, name:'ชาชัก ชาวใต้', salary:15000, department:'กราฟิก', isVisible:false},
                        {id:5, name:'มะม่วง ปลากรอบ', department:'ฝ่ายขาย', isVisible:false},    
                       ]
        }
    },
    methods: {
        toggleVisible(id){
            // console.log('Child ID = ',id);
            this.employees = this.employees.map((item)=>{
                if(item.id === id){
                    return {...item,isVisible:!item.isVisible}
                }
                return item
            })
        },
        removeEmployee(id){
            // console.log(id)
            this.employees = this.employees.filter((item)=>{
                return item.id !== id
            })
        }
    }
    // props: ['employees']
    
}
</script>

<style scoped>
    ul{
        list-style: none;
        margin: 1rem 0;
        padding: 0;
    }
</style>