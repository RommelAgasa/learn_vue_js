<template>

    <h2>Volume Tracker (0 - 20)</h2>
    <h3>Current Volume : {{ volume }}</h3>
    <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
    </div>

</template>


<script>

export default {
    name: 'LearnWatchers',
    data() {
        return {
            volume: 0
        }
    },
    methods: {

    },
    computed: {

    },
    watch: {
        volume(newValue, oldValue){
            if(newValue > oldValue && newValue === 16){
                alert('Listening to a high volume for a long time my damage your hearing.');
            }
        }
    }
}

</script>


<style>
#learn-watchers {
  border: 1px solid #ccc;
  padding: 20px;
  margin-top: 20px;
}
</style>