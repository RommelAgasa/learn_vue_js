<!-- Methods -->

<template>

    <h2>{{ 2 + 3 + 5 }}</h2>

    <h2>Add Method {{ add(2, 3, 5, 1, 4) }}</h2>
    <h2>Multipy method - {{ multipy(baseValue) }}</h2>

</template>


<script>


export default {
    name: 'LearnMethods',
    data(){
        return {
            baseMultiplier: 5,
            baseValue: 2
        }
    },
    methods: {
        add(a, b, c, d, e){ 
            return a + b + c + d + e
        },
        multipy(num) {
            return num * this.baseMultiplier;
        }
    }
}

</script>

<style>
#learn-methods{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>