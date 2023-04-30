<template>
   
    <h1> Stock Application</h1>
    <div v-for="stock of stocks" :key="stock.name" class = "stockapp" >
    
       <SingleStock :stock=stock />

    </div>

</template>
<script>
import SingleStock from './SingleStock.vue'

export default {
    name: 'StockBox',
    props:{
        stocks: Array
    },
    components:{
        SingleStock
    }
    
}
</script>
<style scoped>

h1{
    text-align: center;
    font-size: 50px;
    color: #ab792d;
    font-family: 'Montserrat', sans-serif;
    margin-bottom: 50px;
}

.stockapp{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 50px;
}


</style>
