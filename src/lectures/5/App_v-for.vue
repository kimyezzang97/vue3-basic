<template>
	<div>
		<ul>
			<template v-for="(item, index) in items" :key="item.id">
				<li v-if="item.id % 2 === 0">
					ID: {{ item.id + '인덱스' + index + item.message }}
				</li>
			</template>
		</ul>
		<hr />
		<ul>
			<li v-for="(value, key, index) in myObject" :key="key">
				{{ index + '-' + key + '-' + value }}
			</li>
		</ul>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const items = reactive([
			{ id: 1, message: 'Java' },
			{ id: 2, message: 'Html' },
			{ id: 3, message: 'Css' },
			{ id: 4, message: 'JavaScript' },
		]);

		const myObject = reactive({
			title: '제목',
			author: '홍길동',
			publishedAt: '2016-01-01',
		});
		return { items, myObject };
	},
};
</script>

<style lang="scss" scoped></style>
