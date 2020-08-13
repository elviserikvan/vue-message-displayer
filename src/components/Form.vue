<template>
	<form @submit.prevent="emitMessage">
		<div class="form-group text-center">
			<input v-model="message" type="text" class="form-control" placeholder="Enter a message here">
			<input type="submit" class="mt-5 btn btn-primary btn-lg" value="Send">
		</div>
	</form>
</template>

<script>
	export default {
		name: 'Form',
		data(){
			return {
				message: ''
			}
		},
		methods: {
			emitMessage(){
				this.$emit('show-text', this.message);
			}
		}
	}
</script>
