<template>
	<v-card class="new-participants-card">
		<div class="new-participants-top">
			<div class="new-participants-photo">
				<img :src="require(`@/assets/img/${data.img}.png`)" alt="photo" />
				<div class="new-participants-status"></div>
			</div>
			<div class="new-participants-info">
				<div class="new-participants-name">{{ data.name }}</div>
				<div class="new-participants-location">{{ data.location }}</div>
			</div>
		</div>
		<div class="new-participants-tags">
			<span v-for="(tag, i) in data.tags" :key="tag + i">{{ tag }}</span>
		</div>
	</v-card>
</template>

<script>
export default {
	props: ["data"]
};
</script>

<style lang="scss">
#app .new-participants-card {
	overflow-x: hidden;
	padding: 16px;
	box-shadow: none;
}

.new-participants-tags {
	overflow-x: scroll;
	&::-webkit-scrollbar {
		width: 0 !important;
	}
}

.new-participants-top {
	display: flex;
	margin-bottom: 16px;
}

.new-participants-photo {
	margin-right: 10px;
	position: relative;
}

.new-participants-status {
	position: absolute;
	bottom: 2px;
	right: -4px;
	width: 12px;
	height: 12px;
	background: #00ffc2;
	border: 2px solid #ffffff;

	&--offline {
		background-color: #b6afbc;
	}
}

.new-participants-name {
	margin-bottom: 8px;
	font-weight: bold;
	font-size: 14px;
	line-height: 19px;
	color: #320e3f;
}

.new-participants-location {
	font-weight: 500;
	font-size: 12px;
	line-height: 16px;
	color: #727272;
}

.new-participants-tags {
	display: flex;
	margin-bottom: -16px;

	span {
		display: inline-block;
		padding: 1px 4px;
		margin-right: 4px;
		font-style: normal;
		font-weight: 500;
		font-size: 11px;
		line-height: 14px;
		color: #727272;
		border: 1px solid #f1f1f1;
		border-radius: 2px;
	}
}
</style>
