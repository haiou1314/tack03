<template>
  <div id="app">
    <ul>
      <li v-for="(item, index) in arr" :key="index">
        <span>{{ item }}</span>
        <button @click="del(index)">删除</button>
      </li>
    </ul>
    <button @click="add">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 5, 3],
    }
  },
  methods: {
    add() {
      this.arr.push(Math.floor(Math.random() * 10))
    },
    del(id){
      let index =this.arr.findIndex((item)=>item==id)
      this.arr.splice(index,1)
    }
  },
}
</script>
