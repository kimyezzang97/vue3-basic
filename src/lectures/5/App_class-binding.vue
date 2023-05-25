<template>
	<div>
		<div :class="{ active: isActive }">텍스트입니다.</div>
		<button @click="toggle">toggle</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);

		const toggle = () => {
			isActive.value = !isActive.value;
		};
		return { isActive, toggle };
	},
};
</script>

<style lang="scss" scoped>
.active {
	font-weight: 900;
}
</style>
