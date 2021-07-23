<template>
	<a class="news-item"
		><span>{{ text }}</span
		><ArrowRight
	/></a>
</template>

<script>
import ArrowRight from "@/assets/svg/arrow-right.svg";
export default {
	components: {
		ArrowRight
	},
	props: ["text"]
};
</script>

<style lang="scss">
.news-item {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 12px 7px 12px 16px;
	font-size: 14px;
	font-weight: bold;
	background-color: #fff;
	cursor: pointer;
	width: calc(50% - 12px);

	span {
		white-space: nowrap;
		text-overflow: ellipsis;
		overflow-x: hidden;
		font-size: 14px;
	}

	&:last-child {
		margin-left: auto;
	}
}

@media (max-width: 1140px) {
	.news {
		flex-direction: column;
	}

	.news-item {
		width: 100%;
		margin-right: 0;

		&:first-child {
			margin-bottom: 16px;
		}
	}
}
</style>
