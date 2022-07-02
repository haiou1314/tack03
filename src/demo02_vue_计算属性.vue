<!-- 代码演示 -->
<template>
  <div>
    购物车商品总价：
    <!-- 商品是否大于500 符合条件可使用400的优惠券 否则不可使用 -->
    <p>计算属性computed：计算属性读取的数据是从缓存里面读取如果依赖的数据不发生改变，会一直从缓存里面读取</p>
    {{ totalPrice }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      total: 5,
      price: 98,
      coupon: 400,
    }
  },

  computed: {
    totalPrice() {
      return this.total * this.price >= 500
        ? this.total * this.price - this.coupon
        : this.total * this.price
    },
  },
}
</script>
