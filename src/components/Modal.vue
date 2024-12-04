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

</style>
