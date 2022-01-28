<template>
	<v-container fluid pa-0>
		<v-sheet class="black" width="100vw">
			<v-img
				v-for="i in lenwebp"
				:key="i"
				:src="require('../assets/RAW/Raw' + i + '.webp')"
				eager
				max-width="750px"
				class="mx-auto"
			/>
		</v-sheet>
	</v-container>
</template>

<script>
export default {
	name: "Story",
	props: ["num"],
	data: () => ({ lenwebp: 0 }),
	methods: {
		lengths() {
			const raws = require.context("../assets/RAW/", false, /^.*\.webp$/);
			this.lenwebp = raws.keys().length;
		},
	},
	created() {
		this.lengths();
	},
};
</script>
