<template>
  <div>
    <!-- <router-view></router-view> -->
    <ul>
      <li v-for="(item,key) in data" :key="key">{{item}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      data: []
    }
  },
  mounted: function() {
    this.$axios.get("/api/data").then(res => {
      this.data = res.data
      console.log(this.data)
    })
  }
}
</script>