<template>
	<div class="container">
		<h1 class="m-5 text-center">Simple message displayer</h1>
		<Modal></Modal>
		<Form v-on:show-text="setMessage"></Form>
	</div>
</template>


<script>
	import Form from './Form.vue';
	import Modal from './Modal.vue';

	export default {
		name: 'App',
		methods: {
			setMessage(message) {
				this.$emit('toModal', message);
			}
		},
		components: {
			Form,
			Modal
		}  
	}
</script>
