<template>
	<div class="event">
		<p>{{ text }}</p>
		
	</div>
</template>
<script>
export default {
	name: "EventComponent",
	props: {
		text: String,//name: type of event
	}
}
</script>
<style>
.event { 

	display: flex;
	justify-content: center;
    align-items: center;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #5a5656;
}

.event p {
	margin: 0;
	padding: 0;
	font-size: 16px;
	color: #f2ebeb;
}
</style>