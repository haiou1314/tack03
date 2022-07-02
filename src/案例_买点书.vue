<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="(item, index) in arr" :key="index">
        <span>{{ item['name'] }}</span>
        <button @click="sum(index)">买书</button>
      </li>
    </ul>
    <table border="1" width="500" cellspacing="0">
      <tr v-for="(item, index) in arr" :key="index">
        <th>{{ index + 1 }}</th>
        <th>{{ item.name }}</th>
        <th>{{ item.price }}</th>
        <th>{{ item.count }}</th>
        <th>{{ item.price * item.count }}</th>
      </tr>
    </table>
    <p>总价格为:{{ count }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          name: '水浒传',
          price: 107,
          count: 0,
        },
        {
          name: '西游记',
          price: 192,
          count: 0,
        },
        {
          name: '三国演义',
          price: 219,
          count: 0,
        },
        {
          name: '红楼梦',
          price: 178,
          count: 0,
        },
      ],
    }
  },
  methods: {
    sum(id) {
      this.arr[id]['count']++
    },
  },
  computed: {
    count() {
      return this.arr.reduce((sum, next) => {
        return (sum += next.price * next.count)
      }, 0)
    },
  },
}
</script>
