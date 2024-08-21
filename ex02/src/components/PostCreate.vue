<template>
	<div>
		<!-- <button class="btn btn-primary" @click="$emit('createPost', 1, 2, '김길동')"> -->
		<input v-model="title" type="text" class="form-control" />
		<button class="btn btn-primary" @click="createPost">button</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	emits: ['createPost'],
	setup(props, { emit }) {
		const title = ref('');

		const createPost = () => {
			emit('createPost', title.value);
		};
		return { createPost, title };
	},
};
</script>

<style lang="scss" scoped></style>
