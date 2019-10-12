<template>
  <div id="div">
     {{msg}}
  </div>
</template>

<script>
  import axios from 'axios'
  import data from '../../static/information'
export default {
  name: 'home',
  props: {
    msg:data.type
  },
  methods: {
    getData () {
      var oDiv = document.getElementById('div')
      axios.get('http://localhost:8081/static/information.json',{})
              .then((res)=>{
                oDiv.innerHTML = res.data
              })
    }
  },
  created() {
    this.getData()
  }
}
</script>
<style scoped lang="stylus">

</style>
