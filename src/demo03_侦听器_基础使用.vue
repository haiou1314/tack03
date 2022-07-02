<template>
  <div>
    <p>
      监听：分为浅监听和深监听如果不写deep:true就是浅监听，不会监听到复杂数据类型，immediate:
      true是打开浏览器就开始监听一次而不是等值修改了在监听
    </p>
    <input type="text" v-model="user.name" />
    <br />
    <input type="text" v-model="user.age" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: '',
        age: 0,
      },
    }
  },
  // 目标: 侦听对象
  /*
  语法:
    watch: {
      变量名 (newVal, oldVal){
        // 变量名对应值改变这里自动触发
      },
      变量名: {
        handler(newVal, oldVal){

        },
        deep: true, // 深度侦听(对象里面层的值改变)
        immediate: true // 立即侦听(网页打开handler执行一次)
      }
    }
  */
  watch: {
    user: {
      handler(newVal, oldVal) {
        // user里的对象
        console.log(newVal, oldVal)
      },
      deep: true,
      immediate: true,
    },
  },
}
</script>

<style></style>
