<template>
  <div class="l-header">
    <div class="header" > 
      <SignUp /></div>
  </div>
</template>

<script>
import SignUp from '~/components/SignUp'
import Vue from 'vue'
import Vuex from 'vuex'

export default {
  components: {
    SignUp
  }
}

// 모듈 시스템을 사용하는 경우 Vue.use(Vuex)를 먼저 호출해야합니다.
Vue.use(Vuex);
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  }
})



store.commit('increment')
store.commit('increment')
store.commit('increment')
console.log(store.state.count) // -> 1
</script>
<style scoped>
/* .SignUp{
display: flex;  
justify-content: flex-end;
} */

</style>