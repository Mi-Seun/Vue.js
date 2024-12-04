<template>
	<div class="container" v-if="data && data.length > 0">
	<div v-for="(movie, i) in data" :key="i" class="item">
		<figure>
		<img :src="`${movie.imgUrl}`" :alt="movie.title">
		</figure>
		<div class="info">
		<h3 :style="movie.textRed">{{ movie.title }}</h3>
		<p>{{ movie.year }}</p>
		<button @click="$emit('increseLike', i)">Aime</button>
		<p>
			<button @click="$emit('openModal', i)">Voir plus</button>
			<span>{{ movie.like }}</span>
		</p>
		</div>
	</div>
	</div>
	<p v-else>Aucune donnée disponible</p>
</template>

<script>
	export default {
		name: "MoviesComponent",
		props: {
		data: {
			type: Array,
		},
		},
	};
</script>

<style>
	.container {
		padding: 20px;
	}
</style>
