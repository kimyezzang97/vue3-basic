<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic eligendi,
			doloremque ipsam maxime rem nisi veniam voluptates, soluta fugiat ea saepe
			praesentium, cupiditate consequuntur numquam enim qui quia nesciunt
			minima?
		</div>
		<button @click="fontSize--">-</button>
		<button @click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed } from 'vue';
import { ref } from 'vue';

export default {
	setup() {
		const fontSize = ref(13);
		const styleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontSize.value + 'px',
			};
		});
		return { fontSize, styleObject };
	},
};
</script>

<style lang="scss" scoped></style>
