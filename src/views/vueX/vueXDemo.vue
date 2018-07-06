<template>
  <div>
    <div>
      <h4>从vueX获取的数据：</h4>
      <p>{{ store.name }} :{{ store.count }}</p>
    </div>
    <div>
      <h4>从vueX获取的数据：</h4>
      <p>{{ inStore.state.name }} :{{ inStore.state.count }}</p>
    </div>
  </div>
</template>

<script>
import Vuex from 'vuex'
// 组件内部仓库
const inStore = new Vuex.Store({
  state: {
    count: 1,
    name: '我是在组件内部'
  },
  mutations: {
    increment (state) {
      state.count++
    }
  }
})

export default {
  name: '',
  data () {
    return {
      store: this.$store.state,
      inStore: inStore
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>