<template>

  <!--Step 3 use the component-->
  <MyHeader StockName="Stock Application" authorName="Ramakrishna Bachu" yourName="Ramakrishna Bachu"/> 
  <StockBox :stocks=stocks />
 
</template>

<script>
// Step: 1 Import the components
import MyHeader from './components/MyHeader.vue'
import StockBox from './components/StockBox.vue'


export default{
  name: 'App',

  // Step 2: Register the components
  components:{
    MyHeader,
    StockBox
  },
  data(){
    return {
      stocks: []
    }
  },
  methods:{
    //promoises
    async fetchstocks(){
      const res = await fetch('https://mighty-beach-76714.herokuapp.com/api');
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created(){
      this.stocks = await this.fetchstocks();
  }

  // data() => this.data books
  // method => this.method => fetchbook
  // life cycle hooks created() => call our method here

}
</script>


<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #f5f5f5;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;

}


</style>
