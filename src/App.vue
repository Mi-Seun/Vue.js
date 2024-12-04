<template>
	<Navbar/>

	<Event :text="text"/> <!--속성명(props 변수) = "보낼 값" -->

	<h1>Information du cinema</h1>
	<div v-for="(movie, i) in data" :key="i" class="item">
		<figure>
			<img :src="`${movie.imgUrl}`" :alt="movie.title">
		</figure>


		<div class="info">
			<div>
				<h3 class="bg-yellow" :style="textRed">{{ movie.title}}</h3>
			</div>
			<p>Date de sortie : {{ movie.year}}</p>
			<p>Genre : {{ movie.category}}</p>
			<button 
				@:click="increseLike(i)">Aime
			</button>
			<span>{{ movie.like }}</span>
			<p>
				<button @click="isModal=true; selecteMovie=i">Voir plus</button>
			</p>
		</div>
	</div>
<!-- <Modal /> -->

</template>

<script>
import data from './assets/movies.js';
import NavbarComponent from "./components/Navbar.vue";
import EventComponent from "./components/Event.vue";
//import ModalComponent from "./components/Modal.vue";

export default {
	name: 'App',
	data() {
		return {
			isModal: false,
			data: data,
			selecteMovie: 0,
			text: "coucou aaa bbb",
			}
	},
	methods: { //functions
        increseLike(i) {
			this.data[i].like += 1;
        }
    },
	components: {
		Navbar: NavbarComponent,
		//Modal: ModalComponent,
		Event: EventComponent
    },
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
	margin-bottom: 1rem;
}

p {
	margin-bottom: 0.5rem;
}

button {
	margin-right: 10px;
	margin-top: 1rem;
	padding: 5px 10px;
}

.item {
	width: 100%;
	border-radius: 1px solid;
	display: flex;
	background-color: #f5f5f5;
	padding: 10px;
}

.item img{
	width: 100%;
}

.item figure{
	width: 30%;
	margin-right: 1rem;
}

.item .info {
	width: 100%;
}

.modal{
	background-color: antiquewhite;
	position:fixed;
	top: 0;
	left: 0;
	width: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
}

.modal.inner {
	background-color: rgba(0, 0, 0, 0.8);
    padding: 20px;
    border-radius: 10px;
    width: 80%;
}

</style>
