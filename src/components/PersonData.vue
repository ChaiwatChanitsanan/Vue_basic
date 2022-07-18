<template>
  <CardComponent>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <!-- //แก้ไขเอาออกไม่ใช้แสดงผลแล้ว
    <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>
    
    <template v-slot:card-content>
      <transition name="fade">
        <div v-show="isVisible">
          <p>เงินเดือน :{{ salary }} บาท, ตำแหน่งงาน : {{ department }}</p>
        </div>
      </transition>
    </template>
    -->
    <template v-slot:card-content>
        <p>เพศ : {{gender}} , เงินเดือน :{{ salary }} บาท</p>
        <p>ตำแหน่งงาน : {{ department }}</p>
        <p>ทักษะด้านภาษา : {{skill}}</p>
        <!--<div v-for="(item,index) in skill" :key="index"> {{item}}, </div>-->
    </template>
  </CardComponent>
</template>

<script>
import CardComponent from ".//CardComponent.vue";
export default {
  name: "PersonData",
  components: {
    CardComponent,
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      required: false,
      default: 15000,
    },
    department: {
      type: String,
      required: true,
    },
    gender: {
      type: String,
    },
    skill: {
      type: Array,
    },
  },
};
</script>

<style scoped>
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>