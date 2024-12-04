<template>
	<Navbar />
	<Event :text="text" />
	<Movies 
		:data="data"
		@openModal="isModal=true; selecteMovie=$event"
		@increseLike="increseLike($event)"
	/>
	
	<Modal 
		:data="data" 
		:isModal="isModal" 
		:selecteMovie="selecteMovie" 
		@closeModal="isModal = false" 
	/>
</template>

<script>
// 자식 컴포넌트 가져오기
import data from './assets/movies.js'; // data film
import NavbarComponent from "./components/Navbar.vue"; // navbar
import EventComponent from "./components/Event.vue"; // event box
import ModalComponent from "./components/Modal.vue"; // modal
import MoviesComponent from "./components/Movies.vue"; // movies

export default {
	name: 'App',
	// 데이터
	data() {
	return {
		isModal: false,
		data: data,
		selecteMovie: null,
		text: "Star Wars is back in France",
	};
	},
	// 함수
	methods: { 
	increseLike(i) {
		this.data[i].like += 1;
	}
	},
	// 컴포넌트 등록
	components: { 
	Navbar: NavbarComponent,
	Modal: ModalComponent,
	Event: EventComponent,
	Movies: MoviesComponent,
	},
};
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
	border: 1px ; 
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
	background-color: rgb(145, 210, 226);
	position:fixed;
	top: 60px;
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
