<template>
<div>
	<!--Button -->
	<button id="modal-trigger-btn" class="btn btn-primary d-none" type="button" data-toggle="modal" data-target="#simple-modal">
		Simple text
	</button>


	<!-- Simple modal -->
	<div class="modal fade" id="simple-modal" tabindex="-1" role="dialog" aria-labelledby="modal-label" aria-hidden="true">
		<div class="modal-dialog" role="document">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title" id="modal-label">This website says</h5>
					<button type="button" class="close" data-dismiss="modal" aria-label="Close">
						<span aria-hidden="true">&times;</span>
					</button>
				</div>
				<div class="modal-body">
					<p>{{message}}</p>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
				</div>
			</div>
		</div>
	</div>
</div>
</template>

<script>
	export default {
		name: 'Modal',
		data() {
			return {
				message: ''
			}
		},
		methods: {
			trigger(message) {
				let btn = document.getElementById('modal-trigger-btn');
				this.message = message;
				btn.click();
			}
			
		},
		created() {
			this.$parent.$on('toModal', this.trigger);
		}
	}
</script>
