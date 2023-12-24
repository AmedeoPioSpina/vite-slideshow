<template lang="">
    <section class="slideshow-container">
        <button @click="axiosMoviesFunc()"></button>
    </section>
</template>
<script>
import axios from 'axios';
export default {
    name: "SlideshowComponent",
    components: {

    },
    data() {
        return {
            moviesList: [],
        }
    },
    methods: {
        axiosMoviesFunc(){
            console.log("hello")
            axios.get("https://api.themoviedb.org/3/movie/299534?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=Avengers:%20Endgame")
            .then(resp => this.moviesList= [resp.data])
            .catch(err => console.warn(err));
        },
    }
}
</script>
<style lang="">
    
</style>