<template>
	<header class="header d-flex align-center">
		<v-container>
			<v-row class="align-center">
				<v-col class="header-left">
					<div class="header-logo"><Logo /></div>
				</v-col>
				<v-col class="d-flex align-center pa-0">
					<v-text-field
						hide-details
						dense
						outlined
						class="header-input"
						placeholder="Глобальный поиск"
					></v-text-field>
					<div class="header-user ml-auto d-flex align-center">
						<span class="white--text font-weight-bold">Василиса В.</span>
						<v-avatar size="40" tile class="ml-4">
							<v-img :src="require('@/assets/img/user.png')" alt="alt"></v-img>
						</v-avatar>
					</div>
				</v-col>
			</v-row>
		</v-container>
	</header>
</template>

<script>
import Logo from "../assets/svg/logo.svg";
export default {
	components: {
		Logo
	}
};
</script>

<style lang="scss">
#app {
	.header {
		box-shadow: none;
		min-height: 56px;
		background: radial-gradient(
			53.56% 53.56% at 50% 0%,
			#4a195b 0%,
			#320e3f 100%
		);
		margin-bottom: 24px;

		.row {
			margin: 0;
		}

		.col {
			padding: 0;
		}
		.v-toolbar__content {
			padding: 0 16px;
			height: auto !important;
		}
		.header-input {
			border: none;
			max-width: 552px;

			width: max-content;
			fieldset {
				border: none;
			}
			input {
				background-color: rgba(255, 255, 255, 0.1) !important;
				min-height: 40px;
				padding: 0;
				padding-left: 15px;

				&::placeholder {
					color: #fff;
					font-weight: 500;
				}
			}
		}
		.header-logo {
			line-height: 0;
		}
		.v-input__slot {
			padding: 0;
		}
	}
	.header-left {
		max-width: 264px;
		margin-right: 24px;
	}
}
</style>
