<template>
	<div>
		<label>
			{{ label }}
			<!-- <input v-model="username" type="text" /> -->
			<input v-model="value" type="text" />

			<!-- <input
				:value="modelValue"
				@input="event => $emit('update:modelValue', event.target.value)"
				type="text"
			/> -->
		</label>
	</div>
</template>

<script>
import { computed } from 'vue';

computed;
export default {
	props: ['modelValue', 'label'], // value
	emits: ['update:modelValue'], // @input
	setup(props, { emit }) {
		const value = computed({
			get() {
				return props.modelValue;
			},
			set(value) {
				emit('update:modelValue', value);
			},
		});
		return { value };
	},
};
</script>

<style lang="scss" scoped></style>
