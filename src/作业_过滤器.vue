<template>
  <div>
    <p>国内网站粉丝数量：{{ msg | fn(0) }}</p>
    <p>外国网站粉丝数量：{{ msg | fn(1) }}</p>
    <p>时间：{{ trim | data(0) }}</p>
    <p>时间：{{ trim | data(1) }}</p>
  </div>
</template>

<script>
import moment from 'moment'
export default {
  data() {
    return {
      msg: 1876986,
      trim: 1636450540055,
    }
  },
  filters: {
    fn(val, flog) {
      if (!flog) {
        return val / 10000 + '万'
      }
      if (flog) {
        return val / 1000 + '千'
      }
    },
    data(val, flog) {
      if (!flog) {
        return moment(val).format('YYYY-MM-DD')
      }
      if (flog) {
        return moment(val).format('YYYY/MM/DD')
      }
    },
  },
}
</script>

<style></style>
