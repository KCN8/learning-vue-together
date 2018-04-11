<template>
	<div>
		<h1>MOVIES!!!</h1>
		<form @submit.prevent="searchForMovies()">
			<label for="search">Search</label>
			<input v-model="searchTerm" type="text" name="search" id="search">
			<button type="submit">Search for Movies</button>
		</form>
		<h3>{{searchTerm}}</h3>
		<ul>
			<li v-for="movie of movies" :key="movie.Title">{{ movie.Title }}</li>
		</ul>
	</div>	
</template>

<script>
export default {
  data() {
	  return {
		  searchTerm: '',
		  movies: []
	  }
  },
  methods: {
	  searchForMovies(){
		  const API_URL = `https://omdb-api.now.sh/?s=${this.searchTerm}`
		  fetch(API_URL)
		  	.then(response => response.json())
			.then(response => {
				this.movies = response.Search
				console.log(this.movies)
			})
	  }
  }
}
</script>

<style>

</style>
