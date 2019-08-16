<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>{{title}}</h1>
    <test></test>
      <ve-histogram v-bind:data="chartData"></ve-histogram>
       <div class="btn" v-on:click="changData">改變資料</div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import test from './components/test'
import VeHistogram from 'v-charts/lib/histogram.common'
export default {
  name: 'app',
  data(){
    return{
      title:"hihi",
      chartData: {
          columns: ['日期', '访问用户', '下单用户', '下单率'],
          rows: [
            { '日期': '1/1', '访问用户': 1393, '下单用户': 1093, '下单率': 0.32 },
            { '日期': '1/2', '访问用户': 3530, '下单用户': 3230, '下单率': 0.26 },
            { '日期': '1/3', '访问用户': 2923, '下单用户': 2623, '下单率': 0.76 },
            { '日期': '1/4', '访问用户': 1723, '下单用户': 1423, '下单率': 0.49 },
            { '日期': '1/5', '访问用户': 3792, '下单用户': 3492, '下单率': 0.323 },
            { '日期': '1/6', '访问用户': 4593, '下单用户': 4293, '下单率': 0.78 }
          ]
      }
    
        
    }
    },
  
    components :{
      test,
      VeHistogram
    },
    methods:{
      changData:function(){
        console.log("按下去");
        this.chartData.rows[0].访问用户 +=100
      }
    }
}
        

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
