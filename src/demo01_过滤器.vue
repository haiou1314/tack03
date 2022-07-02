<template>
  <div id="app">
    <h3>vue过滤器分为全局过滤器和局部过滤器</h3>
    <h5>局部过滤器：在当前vue文件生效</h5>
    <p>{{ msg | file }}</p>
    <h5>全局过滤器：在main里面写必须写在所有vue实例文件夹上面不然是找不到的</h5>
    <p>
      挂载在Vue上面的用时需要Vue.filter('过滤器名字'，处理函数)
      过滤器可以传参传了参数就是默认处理的值加传的参例如：你传了2个参加上默认的总共是3个参，过滤器也可以使用多个以管道符|隔开就好
    </p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      msg: 'hello vue',
    }
  },
  filters: {
    file(val) {
      return val.split('').reverse().join('')
    },
  },
}
</script>

<style></style>
