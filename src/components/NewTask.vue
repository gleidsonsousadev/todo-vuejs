<template>
	<div class="new-task">
		<input
			v-model="name"
			@keydown.enter="addTask"
			type="text"
			class="form-element"
			placeholder="Nova tarefa?"
		/>
		<button class="form-element" @click="addTask">+</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			name: '',
		};
	},
	methods: {
        addTask() {
            if ( this.name.length > 0 ) {
                this.$emit('addTask', { name: this.name });
                this.name = '';
            } else {
                return alert('Adicione uma Tarefa!')
            }
		},
	},
};
</script>

<style>
.new-task {
	margin: 35px;
}

.form-element {
	outline: none;
	font-size: 1.5rem;
	border: 1px solid #fff;
	padding: 5px 10px 8px;
	color: #fff;
}

input.form-element {
	max-width: 230px;
	background: #fff2;
	border-top-left-radius: 8px;
	border-bottom-left-radius: 8px;
}

button.form-element {
	border-left: none;
	background-color: #2196f3;
	border-top-right-radius: 8px;
	border-bottom-right-radius: 8px;
}
</style>
