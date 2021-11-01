<template>
  <div>
    <div>당첨 숫자</div>
    <div id="결과창">
      <lotto-ball v-for="ball in winBalls"></lotto-ball>
    </div>
    <div>보너스 </div>
    <lotto-ball></lotto-ball>
    <button v-if="redo">한번더!</button>
  </div>
</template>

<script>
import LottoBall from './components/LottoBall.vue'

export default {
  name: 'App',
  components: {
    LottoBall
  },
  data(){
    return{
      winBalls:[],
      redo:false,
    }
  },
  computed:{

  },
  methods:{

  },
}
</script>

<style>

</style>
