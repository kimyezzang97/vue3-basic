<template>
	<div>
		<div class="card">
			<div class="card-body">
				<!-- type : news, notice -->
				<!-- <span class="badge bg-secondary">{{
					type === 'news' ? '뉴스' : '공지사항'
				}}</span> -->
				<span class="badge bg-secondary"> {{ typeName }}</span>
				<h5 class="card-title red">{{ title }}</h5>
				<p class="card-text">
					{{ contents }}
				</p>

				<a href="#" class="btn" :class="isLikeClass">좋아요</a>
				<!-- <a v-if="isLike" href="#" class="btn btn-danger">좋아요</a>
				<a v-else href="#" class="btn btn-outline-danger">좋아요</a> -->
			</div>
		</div>
	</div>
</template>

<script>
import { computed } from 'vue';

export default {
	props: {
		type: {
			type: String,
			default: 'news',
			validator: value => {
				return ['news', 'notice'].includes(value);
			},
		},
		title: {
			type: String,
			reauired: true,
		},
		contents: {
			type: String,
			reauired: true,
		},
		isLike: {
			type: Boolean,
			default: false,
		},
		obj: {
			type: Object,
			default: () => {
				return {};
			},
		},
	},

	emits: ['toggleLike'],
	setup(props, context) {
		console.log('props.title: ', props.title);
		const isLikeClass = computed(() =>
			props.isLike ? 'btn-danger' : 'btn-outline-danger',
		);
		const typeName = computed(() =>
			props.type === 'news' ? '뉴스' : '공지사항',
		);

		const toggleLike = () => {
			//props.isLike = !props.isLike;
			context.emit('toggleLike');
			console.log('emit');
		};
		return { isLikeClass, typeName };
	},
};
</script>

<style lang="scss" scoped></style>
