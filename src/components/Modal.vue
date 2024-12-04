<template>
	<div class="modal" v-if="isModal">
		<div class="inner">
			<h3>{{data[selecteMovie].title}}</h3>
			<p>Detail de film</p>
			<button @click="$emit('closeModal')">Close</button>
		</div>
	</div>
</template>

<script>
export default {
	name: "ModalComponent",
	props: {
		isModal: Boolean,
        data: Array,
        selecteMovie: Number
    }
}
</script>

<style>
.modal{
	background-color: rgb(201, 204, 161);
	position:fixed;
	top: 60px;
	width: 56.85%;
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 4rem;
}

.modal.inner {
	background-color: rgba(0, 0, 0, 0.8);
    padding: 20px;
    border-radius: 10px;
    width: 80%;
}

</style>
