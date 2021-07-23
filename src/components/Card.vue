<template>
	<v-card class="card">
		<div>
			<v-card-text v-if="data.date">
				<div class="card-date">{{ data.date }}</div>
				<div class="card-label">Zoom</div>
			</v-card-text>
			<v-card-title>
				{{ data.title }}
			</v-card-title>

			<div class="card-category d-flex align-center">
				<Avatar v-if="data.isEvent" />
				<v-img
					v-if="data.helpImg"
					:src="require(`@/assets/img/${data.helpImg}.png`)"
					class="card-avatar"
				></v-img>
				{{ data.category }}
			</div>
		</div>
		<v-card-actions>
			<template v-if="data.isEvent">
				<div class="card-images">
					<v-img
						v-for="image in data.images"
						:key="image"
						:src="require(`@/assets/img/${image}.png`)"
					>
					</v-img>
					<span v-if="data.others">+{{ data.others }}</span>
				</div>
				<div class="card-people">
					<People />
					Иду!
				</div>
			</template>

			<template v-else>
				<div class="card-feedback d-flex align-center">
					<div class="card-feedback-item mr-2 d-flex align-center">
						<div class="mr-1"><Commemnt /></div>
						{{ data.comments }}
					</div>
					<div class="card-feedback-item mr-2 d-flex align-center">
						<div class="mr-1"><Ok /></div>
						{{ data.comments }}
					</div>
				</div>
			</template>
		</v-card-actions>
	</v-card>
</template>

<script>
import Avatar from "@/assets/svg/avatar.svg";
import People from "@/assets/svg/people.svg";
import Commemnt from "@/assets/svg/comment.svg";
import Ok from "@/assets/svg/ok.svg";
export default {
	components: {
		Avatar,
		People,
		Commemnt,
		Ok
	},
	props: ["data"]
};
</script>

<style src="@/assets/scss/Card.scss" lang="scss"></style>
