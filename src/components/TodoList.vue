<template>
	<div class="todo-item" v-for="todo in todos" :key="todo">
		<div>
			<h2>{{ todo.title }}</h2>
			<p>{{ todo.description }}</p>
		</div>
		<button @click="deleteTodo(todo.id)" class="btn">Delete</button>
	</div>
</template>

<script>
export default {
	props: {
		todos: {
			type: Array,
			required: true,
		},
	},
	methods: {
		deleteTodo(todoID) {
			return this.$emit("deleteTodo", todoID);
		},
	},

	emits: ["deleteTodo"],
};
</script>

<style scoped>
.todo-item {
	display: flex;
	justify-content: space-between;
	margin-bottom: 20px;
	border: 1px solid #4fc08d;
	padding: 10px;
	border-radius: 3px;
	background: white;
	width: 100%;
	align-items: center;
}

h2 {
	font-size: 22px;
	margin-bottom: 15px;
}

.btn {
	height: 25px;
	border: 0;
	padding: 5px;
	transition: all 1 ease-in;
	cursor: pointer;
}
.btn:hover {
	background: red;
	color: white;
}
</style>
