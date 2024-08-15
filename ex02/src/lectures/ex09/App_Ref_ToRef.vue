<template>
	<div>
		<h2>author: {{ author }}</h2>
		<h2>title: {{ title }}</h2>
	</div>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 지금 바로 이 책을 읽습니다.',
			price: '무료',
		});

		const { author, title } = toRefs(book);

		return {
			author,
			title,
			book,
		};
	},
};
</script>

<style lang="scss" scoped></style>
