<!-- List Rendering-->

<template>

    <!-- <h2 v-for="name in names" :key="name">{{  name }}</h2> -->

    <h2 v-for="(name, index) in names" :key="name">{{ index }} - {{ name }}</h2>
    
    <h2 v-for="name in fullNames" :key="name.firstName">{{ name.firstName }} {{  name.lastName }}</h2>


    <div v-for="actor in actors" :key="actor.name">
        <h2>{{ actor.name }}</h2>
        <h2 v-for="movie in actor.movies" :key="movie">{{ movie }}</h2>
    </div>

    <div v-for="info in myInfo" :key="info">
        <h2>{{ info }}</h2>
        <h2 v-for="hobby in info.hobbies" :key="hobby">{{ hobby }}</h2>
    </div>

    <template v-for="name in names" :key="name">
        <h2>{{ name }}</h2>
        <hr/>
    </template>


    <template v-for="name in names" :key="name">
        <h2>{{  name }}</h2>
        <input placeholder="Last Name">
        <hr/>
    </template>
    <button @click="shuffleNames">Shuffle</button>
    

    <!-- Conditional Rendering -->
     <template v-for="name in names" :key="name">
        <h2 v-if="name === 'Kyle'">{{ name }}</h2>
    </template>


</template>

<script>

export default {
    name: 'ListRenderingView',
    data(){
        return {
            names: ['Kenneth', 'Kyle', 'Rommel'],
            fullNames: [
                {firstName: 'Kenneth', lastName: 'Inda'},
                {firstName: 'Kyle', lastName: 'Basta'},
                {firstName: 'Rommel', lastName: 'Agasa'},
            ],
            actors: [
                {
                    name: 'Brad Pitt',
                    movies: ['Fight Club', 'Ocean\'s Eleven', 'Once Upon a Time in Hollywood']
                },
                {
                    name: 'Leonardo DiCaprio',
                    movies: ['Inception', 'The Revenant', 'Titanic']
                },
                {
                    name: 'Scarlett Johansson',
                    movies: ['Lost in Translation', 'Marriage Story', 'Black Widow']
                }
            ],
            myInfo: {
                name: 'Rommel Agasa',
                age: 25,
                hobbies: ['Coding', 'Gaming', 'Traveling']
            }
        }
    },
    methods: {
        shuffleNames(){
            console.log(this.names);
            for (let i = this.names.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [this.names[i], this.names[j]] = [this.names[j], this.names[i]];
            }
        }
    }
}
</script>

<style>

.list-rendering{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

</style>