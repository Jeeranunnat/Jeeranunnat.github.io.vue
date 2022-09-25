<template>
  <Card>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <template v-slot:card-botton>
      <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>
    <template v-slot:card-content>
      <transition name="fade">
        <div v-show="isVisible">
          <p>เงินเดือน: {{ salary }} บาท ตำแหน่งงาน: {{ department }}</p>
        </div>
      </transition>
    </template>
  </Card>
</template>

<script>
import Card from "./Card.vue";
export default {
  name: "Person",
  components: { Card },
  methods: {
    showDescription(id) {
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      this.$emit("delete", id);
    },
  },
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 15000,
    },
    department: {
      type: String,
    },
    isVisible: {
      type: Boolean,
    },
  },
  // data(){
  //     return{
  //         message: 'ข้อมูลพนักงานแต่ละคน'
  //     }
  // }
};
</script>

<style scoped>
/* h1 {
  color: red;
} */
/* li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
} */
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1rem 1rem 2rem rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>