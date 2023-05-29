<template>
	<div>
		<input type="text" @keyup.enter="appTodo" value="" />
		<ul>
			<li v-for="(todo, index) in todos" :key="index">
				{{ todo }}
			</li>
		</ul>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const todos = reactive([]);

		const appTodo = e => {
			todos.push(event.target.value);
			event.target.value = '';
			event.target.focus();
		};
		return { todos, appTodo };
	},
};
</script>

<style lang="scss" scoped></style>
