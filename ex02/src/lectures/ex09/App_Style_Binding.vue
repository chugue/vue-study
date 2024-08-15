<template>
	<div>
		<div :style="StyleObject">
			Lorem, ipsum dolor sit amet consectetur adipisicing elit. Asperiores
			blanditiis tempora voluptates quibusdam ut qui nisi assumenda, fuga, fugiat
			hic voluptatum sapiente officiis saepe, dolores amet perferendis nihil. Quod,
			iste?
		</div>
		<button @click="fontSize--">-</button>
		<button @click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		// const StyleObject = reactive({
		// 	color: 'red',
		// 	fontSize: '20px',
		// });

		const fontSize = ref(13);
		const StyleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontSize.value + 'px',
			};
		});

		return { StyleObject, fontSize };
	},
};
</script>

<style lang="scss" scoped></style>
