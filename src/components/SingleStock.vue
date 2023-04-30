<template>
    <!-- write a good template with animations and cool looking stock details wityh below attributes-->
    <div :class="[stock.change > 0 ? 'green' : 'red', 'stock-card']">
    <h2>Name : {{ stock.name }}</h2>
    <h4>Price : {{ stock.price }}</h4>
    <h4>Change : {{ stock.change }}</h4>
    <h4>Percent Change : {{ stock.percentChange }}</h4>
    <h4>Volume : {{ stock.volume }}</h4>
    <div class="up-icon" v-if="stock.percentChange > 20"></div>
  </div>
</template>

<script>

export default{
    name: 'SingleStock',
    props:{
        stock: Array
    }
}
</script>

<style scoped>

  .stock-card {
    background-image: linear-gradient(to top, #fbc2eb 0%, #a6c1ee 100%);
    color: #ab792d;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
    height: 300px;
    width: 600px;
  }

  .stock-card:hover {
    transform: translateY(-5px);
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  }

  .stock-card:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: -1;
    background-image: linear-gradient(-20deg, #2b5876 0%, #4e4376 100%);
    opacity: 0.8;
    transition: all 0.3s ease;
  }

  .stock-card:hover:before {
    opacity: 1;
    transform: scale(1.2);
  }

  .stock-card:hover .up-icon {
    transform: translateY(-10px);
    opacity: 1;
  }

  .up-icon {
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    opacity: 0;
    transition: all 0.3s ease;
  }

  .up-icon:before {
    content: "\25B2"; /* Unicode for the up arrow symbol */
    font-size: 1.5rem;
    color: #00e676; /* Green color */
  }

  h2 {
    margin: 0;
    font-size: 2rem;
  }

  h4 {
    margin: 10px 0;
    font-size: 1rem;
    font-weight: normal;
  }

</style>