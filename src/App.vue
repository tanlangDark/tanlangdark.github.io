<script setup>
import HelloWorld from './components/HelloWorld.vue'
import DragDialog from './components/Card.vue'
import { ref } from 'vue'

const dialogDrag = ref(false);

const myArray = ref([
  {
    name: "张三",
    state: "0",
    id: 1,
  },
  {
    name: "李四",
    state: "0",
    id: 2,
  },
  {
    name: "王五",
    state: "0",
    id: 3,
  },
  {
    name: "赵六",
    state: "0",
    id: 4,
  },
  {
    name: "AK、dadada",
    state: "0",
    id: 5,
  },
]);

const onClick = () => {
  dialogDrag.value = true;
};
// 提交
const submitDrag = () => {};
// 拖动前
const onDragStart = () => {};
// 拖动后
const onDragEnd = () => {};
// 复选框
const checkoutChange = (element, index) => {};
</script>

<template>
  <el-button @click="onClick">弹框</el-button>

  <DragDialog
    v-model:dragDialog="dialogDrag"
    :dragArr="myArray"
    @submitDrag="submitDrag"
    @checkoutChange="checkoutChange"
    @onDragStart="onDragStart"
    @onDragEnd="onDragEnd"
  ></DragDialog>
  <HelloWorld/>
</template>
