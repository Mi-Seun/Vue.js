<template>
	<nav class="navbar">
		<a href="#">Accuil</a>
		<a href="#">Films</a>
		<a href="#">About</a>

	</nav>
</template>

<script>
export default {
	name: 'NavbarComponent',
}

</script>

<style>
.navbar {
	background-color: #d7be03;
    color: white;
    overflow: hidden;
	padding: 10px 16px;
	text-align: center;
	box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2);
	position: sticky;
	top: 0;
    z-index: 100;
	transition: top 0.5s;
}

.navbar a {
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
	transition: background-color 0.3s;
	font-size: 17px;
	border-radius: 5px;
	margin: 0 5px;
	position: relative;
	left: 0;
	top: 0;
	z-index: 100;
	background-color: transparent;
	cursor: pointer;
}
</style>