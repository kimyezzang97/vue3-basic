<template>
	<div>
		<p>author : {{ author }}</p>
		<p>title : {{ title }}</p>
	</div>
</template>

<script>
import { reactive, toRef } from 'vue';

export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 지금 바로 이책을 읽습니다.',
			price: '무료',
		});
		// 만약 toRefs나 toRef로 받지 않고 그냥 받으면 반응형이 되지 않는다.
		// const {author, title} = toRefs(book); 한번에 여러가지를 반응형으로 받는 방법
		// 하나씩 받는 방법
		const author = toRef(book, 'author');
		const title = toRef(book, 'title');

		return { author, title, book };
	},
};
</script>

<style lang="scss" scoped></style>
