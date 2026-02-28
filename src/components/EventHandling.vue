<template>

    <h2>{{  name }}</h2>
    <div>
        <button @click="changeName($event), increment(1, $event)">Change Name</button>
    </div>

    <h2>{{ count }}</h2>
    <div>
        <button @click="increment(1, $event)">Increment</button>
        <button @click="decrement(1)">Decrement</button>
    </div>



    
</template>


<script>

export default{
    name: 'EventHandling',
    data(){
        return{
            name: 'Rommel',
            count: 0,
        }
    },
    methods:{
        changeName(event){
            this.name = 'Batman';
            console.log(event);
        },
        increment(num, event){
            this.count += num;
            console.log(event);
        },
        decrement(num){
            this.count -= num;
        }
    }
}

</script>


<style>
#event-handling{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>