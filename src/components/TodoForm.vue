<template>
	<form @submit.prevent>
		<input v-model="todo.title" placeholder="Title " />
		<input v-model="todo.description" placeholder="Description" />
		<button @click="createTodo">
			Create a new todo!
		</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			todo: {
				title: "",
				description: "",
			},
		};
	},
	methods: {
		createTodo() {
			this.todo.id = new Date();
			this.$emit("createTodo", this.todo);
			this.todo = {
				title: "",
				description: "",
			};
		},
	},
};
</script>

<style scoped>
form {
	display: flex;
	flex-direction: column;
}
input {
	height: 40px;
	margin-bottom: 20px;
	font-size: 16px;
	padding: 10px;
}

button {
	margin-bottom: 20px;
	height: 40px;
	border: 0;
	background: #ffffff;
	cursor: pointer;
	box-shadow: 0px 6px 8px -4px rgba(123, 255, 167, 0.25);
	font-size: 18px;
	border: 1px solid rgba(123, 255, 167, 0.3);
	background: #4fc08d;
	color: #ffffff;
}
</style>
