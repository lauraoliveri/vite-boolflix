<script>
/* 
  Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
  1) Importazione del componente
  2) Dichiarazione del componente
  3) Utilizzo del componente
*/
// 1) Importazione del componente
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import SingleMovie from './components/SingleMovie.vue';
import axios from 'axios';



export default {
  data() {
    return { 
      store,
      Movies: []
    }
  },
  // 2) Dichiarazione del componente
  components: {
    AppHeader,
    AppMain,
    SingleMovie
  },
  created() {
    this.performSearch();
  },
  methods: {
      performSearch() {
        axios
        .get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'e1d9f6392b861b67ce93fbe118964004',
          query: this.search
          
        }
      })
        .then((res)=> {
          console.log(res);
          
          this.Movies= (res.data.results) 
        })
        .catch((err) => {
          console.error(err);
        })

        
    }
  }
}

</script>

<template>
  <div>
    <!-- 3) Utilizzo del componente -->
    <AppHeader  @search="performSearch()" />
    
    <main>
     <AppMain/>

     <SingleMovie v-for="(movie, i) in Movies" :key="i" :Movie="movie"/>

    </main>
  </div>
</template>

<style lang="scss">
@use 'assets/scss/main' as *;
// Import all of Bootstrap's CSS
@import "bootstrap/scss/bootstrap";
</style>
