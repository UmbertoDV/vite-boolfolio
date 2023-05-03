<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";

export default {
	data() {
		return {
			title: "Hello World",
			cards: [],
		};
	},
	components: {
		AppHeader,
	},

	methods: {
		fetchCards() {
			axios.get("http://127.0.0.1:8000/api/cards").then((response) => {
				this.cards = response.data;
			});
		},
	},

	created() {
		this.fetchCards();
	},
};
</script>

<template>
	<AppHeader></AppHeader>
	<h1>{{ title }}</h1>
	<ul>
		<li v-for="card in cards">{{ card.title }}</li>
	</ul>
</template>

<style lang="scss" scoped>
//SCSS
</style>
