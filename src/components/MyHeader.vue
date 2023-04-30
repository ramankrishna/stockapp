<template>
<div>
    <h1> {{name}} </h1>
    <h4> {{price}} </h4>
    <h4> {{change}} </h4>
</div>
</template>

<script>

export default{ // Exporting Default Object
    name: 'MyHeader',
    props:{ 

        name:String,
        price:Number,
        change: Number
    }
}

</script>

<style scoped>

div{
    text-align: center;
}

</style>