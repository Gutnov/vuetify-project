<template>
	<v-app>
		<Header />
		<v-container>
			<div class="wrapper d-flex">
				<div class="left-content flex-grow-1">
					<Sidebar />
				</div>
				<div class="right-content flex-grow-1">
					<v-select
						class="white select mb-6"
						hide-details
						:items="selectItems"
						label="Справочник Места"
						solo
					>
						<template v-slot:append><SelectIcon /></template>
					</v-select>
					<HeadingSection title="Новости" firstText="Сегодня" firstNumber="2" />
					<div class="news mb-6">
						<NewsItem text="Mission Space подняли 100 мультов и не знают..." />
						<NewsItem
							text="Как сделать питч презентацию и не уснуть во вр..."
						/>
					</div>
					<HeadingSection
						title="Ближайшие события"
						firstText="Всего:"
						firstNumber="45"
						secondText="Сегодня:"
						secondNuber="4"
					/>
					<v-row no-gutters class="grid-container mb-6">
						<v-col clas="grid-item" v-for="c in eventsCards" :key="c.title">
							<Card :data="c" />
						</v-col>
					</v-row>
					<HeadingSection
						title="Взаимопомощь"
						firstText="Всего"
						firstNumber="134"
					/>
					<v-row no-gutters class="grid-container mb-6">
						<v-col clas="grid-item" v-for="c in mutualHelpCards" :key="c.title">
							<Card :data="c" />
						</v-col>
					</v-row>
					<HeadingSection title="Новые участники" />
					<v-row no-gutters class="grid-container mb-6">
						<v-col
							clas="grid-item"
							v-for="c in newParticipantCards"
							:key="c.name"
						>
							<NewParticipantCard :data="c" />
						</v-col>
					</v-row>
				</div>
			</div>
		</v-container>
	</v-app>
</template>

<script>
import Header from "@/components/Header";
import Sidebar from "@/components/Sidebar";
import HeadingSection from "@/components/HeadingSection";
import NewsItem from "@/components/NewsItem";
import Card from "@/components/Card";
import NewParticipantCard from "@/components/NewParticipantCard";
import SelectIcon from "@/assets/svg/select-icon.svg";

import { eventsCards, mutualHelpCards, newParticipantCards } from "@/data";

export default {
	name: "App",
	components: {
		Header,
		Sidebar,
		HeadingSection,
		SelectIcon,
		NewsItem,
		Card,
		NewParticipantCard
	},

	data() {
		return {
			selectItems: ["item1", "item2", "item3"],
			eventsCards,
			mutualHelpCards,
			newParticipantCards
		};
	}
};
</script>
<style src="@/assets/scss/App.scss" lang="scss"></style>
