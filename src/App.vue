<template>
  <div>
    <div>당첨 숫자</div>
    <div id="결과창">
      <lotto-ball v-for="ball in winBalls" number="10" :key="ball"></lotto-ball>
    </div>
    <div>보너스 </div>
    <lotto-ball v-if="bonus"></lotto-ball>
    <button v-if="redo">한번더!</button>
  </div>
</template>
  
<script>
  function getWinNumber() {
    console.log('getWinNumbers');
    const candidate = Array(45).fill().map((v,i) => i+1);
    const shuffle = [];
    while(candidate.length > 0) {
      shuffle.push(candidate.splice(Math.floor(Math.random() * candidate.length),1)[0]);
    }
    const bonusNumber = shuffle[shuffle.length-1];
    const winNumbers = shuffle.slice(0, 6).sort((p,c) => p-c);
    return [...winNumbers, bonusNumber];
  }
import LottoBall from './components/LottoBall.vue'

export default {
  name: 'App',
  components: {
    LottoBall
  },
  data(){
    return{
      winBalls:[],
      bonus:null,
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
