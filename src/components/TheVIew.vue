<template>
	<div>
		<main>
			<div class="container">
				<div class="container text-center py-4">
					<div class="row g-3">
						<div class="col col-4">
							<AppCard />
						</div>
						<div class="col col-4"><AppCard /></div>
						<div class="col col-4"><AppCard /></div>
						<div class="col col-4"><AppCard /></div>
						<div class="col col-4"><AppCard /></div>
						<div class="col col-4"><AppCard /></div>
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
import AppCard from './AppCard.vue';

export default {
	setup() {
		return {};
	},
	components: { AppCard },
};
</script>

<style lang="scss" scoped></style>
