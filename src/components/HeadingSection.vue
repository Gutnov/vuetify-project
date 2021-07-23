<template>
	<div class="heading-section mb-4">
		<h2 class="heading-section__title">
			{{ title }}
		</h2>
		<div v-if="firstText" class="heading-section__info">
			{{ firstText }}:<span> {{ firstNumber }} </span>
		</div>
		<div v-if="secondText" class="heading-section__info">
			{{ secondText }}:<span> {{ secondNumber }} </span>
		</div>
		<div class="heading-section__all ml-auto">Смотреть все</div>
	</div>
</template>

<script>
export default {
	props: ["title", "firstText", "secondText", "firstNumber", "secondNumber"]
};
</script>

<style lang="scss">
.heading-section {
	display: flex;
	align-items: center;
}

.heading-section__title {
	margin-bottom: 0;
	margin-right: 13px;
	font-size: 20px;
	line-height: 22px;
	font-weight: 700;
	color: #4a0a52;
}

.heading-section__info {
	margin-right: 4px;
	font-size: 12px;
	line-height: 14px;
	color: #727272;

	span {
		margin-left: 4px;
		color: #4a0a52;
		font-size: 12px;
	}
}

.heading-section__all {
	margin-left: auto;
	text-decoration: underline;
	font-weight: 600;
	cursor: pointer;
	font-size: 13px;

	&:hover {
		text-decoration: none;
	}
}
</style>
