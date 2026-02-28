<template>

    <h2>Volume Tracker (0 - 20)</h2>
    <h3>Current Volume : {{ volume }}</h3>
    <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
    </div>

    <input type="text" v-model="movie">
    <input type="text" v-model="movieDetails.genre">
    <input type="text" v-model="movieDetails.director">

    <div>
        <button @click="movieList.push({name: 'Wonder Woman', genre: 'Action', director: 'Patty Jenkins'})">Add Movie</button>
    </div>

</template>


<script>

export default {
    name: 'LearnWatchers',
    data() {
        return {
            volume: 0,
            movie: 'Batman',
            movieDetails: {
                genre: '',
                director: ''
            },
            movieList: [
                { name: 'Batman', genre: 'Action', director: 'Christopher Nolan' },
                { name: 'Inception', genre: 'Sci-Fi', director: 'Christopher Nolan' },
                { name: 'The Dark Knight', genre: 'Action', director: 'Christopher Nolan' }
            ]
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
        },
        movie: {
            handler(newValue){
                console.log('Calling API with movie name: ' + newValue)
            },
            immediate: true, // this will call the handler immediately when the component is created
        },
        movieDetails: {
            handler(newValue){
                console.log('Movie genre: ' + newValue.genre);
                console.log('Movie director: ' + newValue.director);
            },
            deep: true // this will watch for changes in nested properties of movieDetails
        },
        movieList: {
            handler(newValue){
                console.log('Movie list updated: ' + JSON.stringify(newValue));
            },
            deep: true
        }
        // movie(newValue){
        //     console.log('Calling API with movie name: ' + newValue)
        // }
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