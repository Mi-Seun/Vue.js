<template>
	<h1>Cinema</h1>
	<div v-for="(movie, i) in data" :key="i" class="item">
		<figure>
			<img :src="`${movie.imgUrl}`" :alt="movie.title">
		</figure>
		<div>
			<h3 class="bg-yellow" :style="textRed">{{ movie.title}}</h3>
		</div>
		<div class="info">
			<p>Date de sortie : {{ movie.year}}</p>
			<p>Genre : {{ movie.category}}</p>
			<button 
				@:click="increseLike(i)">Aimer
			</button>
			<span>{{ movie.like }}</span>
		</div>
	</div>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			data: [
				{
					title: "Star Wars",
					year: '1977',
					category: "Science Fiction",
					textRed:  "color: blue",
					like: 0,
					imgUrl: "./assets/images/1.jpg",
				},
				{
					title: "Avatar",
					year: '2009',
					category: "Science Fiction/Fantasy",
					textRed:  "color: green",
					like: 0,
					imgUrl: "./assets/images/2.jpg",
				},
				{			
					title: "Inception",
					year: '2010',
					category: "Action/Thriller",
					textRed:  "color: red",
					like: 0,
					imgUrl: "./assets/images/3.jpg",
				},
				{
					title: "The Dark Knight",
                    year: '2008',
                    category: "Action/Crime",
                    textRed:  "color: orange",
					like: 0,
					imgUrl: "./assets/images/4.jpg",
				}
			]
		}
	},
	methods: {
        increseLike(i) {
			this.data[i].like += 1;
        }
    }
}
</script>

<style>
* {
	margin: 0;
    padding: 0;
    box-sizing: border-box;
}
body {
	font-family: Arial, sans-serif;
	max-width: 786px;
	margin: auto;
	padding: 20px;
}

h1, h2, h3 {
	text-align: center;
	margin-bottom: 20px;
	font-weight: bold;
	color: #333;
	text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
	text-transform: uppercase;
	letter-spacing: 1px;
	line-height: 1.2;
}

.item {
    margin-bottom: 30px;
	background-color: rgba(255, 255, 255, 0.9);
	border-radius: 5px;
	box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
	align-self: start;
	text-align: center;
}

img {
	width: 100%;
    max-width: 300px;
    object-fit: cover;
    border-radius: 5px;
	transition: transform 0.3s ease-in-out;
	box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
	align-items: center;

}
.info {
	margin-top: 10px;
	display: flex;
	align-items: center;
	justify-content: space-between;
	flex-wrap: wrap;
	padding: 10px;
	background-color: rgba(255, 255, 255, 0.8);
	border-radius: 5px;

}

button {
	background-color: red;
	color: aliceblue;
	padding: 10px;
	border: none;
	border-radius: 5px;
	cursor: pointer;
	transition: background-color 0.3s ease-in-out;
	margin-right: 10px;
}

</style>
