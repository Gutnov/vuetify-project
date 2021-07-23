<template>
	<v-list class="sidebar py-0">
		<v-list-item-group class="py-6">
			<v-list-item
				v-for="item in menuItems"
				:key="item.component"
				class="px-6 font-weight-bold"
				:class="{ active: item.active }"
				:disabled="item.disabled"
			>
				<v-list-item-icon class="ma-0 mr-4">
					<component :is="item.component"></component>
				</v-list-item-icon>
				<v-list-item-content class="pa-0">
					{{ item.text }}
				</v-list-item-content>
			</v-list-item>
			<div class="devider"><span></span></div>
			<v-list-item class="px-6 font-weight-bold">
				<v-list-item-icon class="ma-0 mr-4"><myContacts /> </v-list-item-icon>
				<v-list-item-content class="pa-0">Мои контакты </v-list-item-content>
			</v-list-item>
			<v-list-item class="px-6 font-weight-bold">
				<v-list-item-icon class="ma-0 mr-4"><Unicorn /> </v-list-item-icon>
				<v-list-item-content class="pa-0"> Openland (чат)</v-list-item-content>
			</v-list-item>
		</v-list-item-group>
	</v-list>
</template>

<script>
import Navigator from "@/assets/svg/navigator.svg";
import Events from "@/assets/svg/events.svg";
import Participants from "@/assets/svg/participants.svg";
import Communities from "@/assets/svg/communities.svg";
import PerfectStorm from "@/assets/svg/perfect-storm.svg";
import MutualAssistance from "@/assets/svg/mutual-assistance.svg";
import University from "@/assets/svg/university.svg";
import Library from "@/assets/svg/library.svg";
import Unicorn from "@/assets/svg/unicorn.svg";
import myContacts from "@/assets/svg/my-contacts.svg";
export default {
	components: {
		Navigator,
		Events,
		Participants,
		Communities,
		PerfectStorm,
		MutualAssistance,
		University,
		Library,
		Unicorn,
		myContacts
	},
	data() {
		return {
			menuItems: [
				{ text: "Навигатор", component: "Navigator", active: true },
				{ text: "События (beta)", component: "Events" },
				{ text: "Участники", component: "Participants" },
				{ text: "Сообщества", component: "Communities" },
				{ text: "Идеальный штурм", component: "PerfectStorm" },
				{ text: "Взаимопомощь", component: "MutualAssistance" },
				{ text: "Университет", component: "University", disabled: true },
				{ text: "Библиотека", component: "Library", disabled: true }
			]
		};
	}
};
</script>

<style lang="scss">
#app .sidebar {
	.v-list-item {
		min-height: max-content;
		margin-bottom: 22px;

		&:last-child {
			margin-bottom: 0;
		}

		&:hover,
		&.active {
			color: #9b51e0;
			svg path {
				fill: #9b51e0;
			}
		}
	}
	.v-list-item__icon {
		align-self: center;
		min-width: max-content;
	}

	.devider {
		padding: 0 24px;
		margin-bottom: 24px;
		display: flex;

		span {
			flex-grow: 1;
			height: 1px;
			background-color: #cab3cd;
		}
	}
	.v-list-item--disabled svg {
		opacity: 0.5;
	}
}
</style>
