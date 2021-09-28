<template>
	<main>
		<div class="content">
			<h1 class="content-title">Manage your time!</h1>
			<TodoForm @createTodo="createTodo" />
			<TodoList :todos="todos" @deleteTodo="deleteTodo" />
		</div>
	</main>
</template>

<script>
import TodoForm from "@/components/TodoForm.vue";
import TodoList from "@/components/TodoList.vue";
export default {
	name: "App",
	components: {
		TodoForm,
		TodoList,
	},
	data() {
		return {
			todos: [
				{ id: "1", title: "First todo", description: "First todo description" },
				{ id: "2", title: "Second todo", description: "Second todo description" },
			],
		};
	},
	methods: {
		createTodo(todo) {
			this.todos.push(todo);
		},
		deleteTodo(todoID) {
			this.todos = this.todos.filter((todo) => todo.id !== todoID);
		},
	},
};
</script>

<style>
* {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

.content-title {
	text-align: center;
	margin-bottom: 20px;
}

main {
	display: flex;
	align-items: center;
	justify-content: center;
	width: 100%;
	height: 100%;
	min-height: 100vh;
	background: #4fc08d;
	padding: 20px;
}

.content {
	max-width: 600px;
	width: 100%;
	display: flex;
	flex-direction: column;
	background: rgb(255, 255, 255);
	padding: 20px;
	border: 1px solid #4fc08d;
	border-radius: 3px;
	box-shadow: 6px 8px 15px 2px rgba(0, 0, 0, 0.25);
}
</style>
