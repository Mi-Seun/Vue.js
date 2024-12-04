<template>
	<div class="event" :class="{ show : isOpen }"> <!-- 상태변수 class -->
		<p>{{ text }}</p>
		<button @click="isOpen=false">X</button>
	</div>
</template>
<script>
export default {
	name: "EventComponent",
	props: {
		text: String,//name: type of event
		isEventOpen: Boolean,
	},
	data() {
		return {
            isOpen: true
        }
	}
}
</script>

<style>
.event { 
	display: none;
	justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #ccccc6;
}

.show {
	display: flex;
}

.event p {
	margin: 0;
	padding: 0;
	font-size: 16px;
	color: #030303;
}

.event button {
	border: 1px solid;
    background-color: #f2ebeb;
    font-size: 16px;
    cursor: pointer;
}
</style>