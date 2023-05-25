<template>
	<div>
		<p>{{ message }}</p>
		<button @click="addMessage">add Click</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	// primitive 변수 적용
	setup() {
		let message = ref('Hello Vue');
		const addMessage = () => {
			message.value += '!';
		};
		return { message, addMessage };
	},
};
</script>

<style lang="scss" scoped></style>
