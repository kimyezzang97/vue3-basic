<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
	</div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLecture = computed(() => {
			return teacher.lectures.length > 0 ? '있음 :)' : '없음 ㅜㅜ';
		});

		const existLecture = () =>
			teacher.lectures.length > 0 ? '있음 :)' : '없음 ㅜㅜ';
		return { hasLecture, existLecture, teacher };
	},
};
</script>

<style lang="scss" scoped></style>
