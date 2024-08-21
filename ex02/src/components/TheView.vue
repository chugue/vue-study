<template>
	<main>
		<div class="container py-4">
			<PostCreate @create-post="createPost"></PostCreate>
			<div class="row g-3">
				<div v-for="post in posts" :key="post.id" class="col col-4">
					<AppCard
						:title="post.title"
						:contents="post.contents"
						:is-like="post.isLike"
						:type="post.type"
						@toggle-like="post.isLike = !post.isLike"
					></AppCard>
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import { reactive } from 'vue';
import AppCard from './AppCard.vue';
import PostCreate from './PostCreate.vue';

export default {
	components: {
		AppCard,
		PostCreate,
	},
	setup() {
		const obj = reactive({
			title: '제목2',
			contents: '내용2',
		});

		const posts = reactive([
			{
				id: 1,
				title: '제목1',
				contents: '내용1',
				isLike: true,
				type: 'news',
			},
			{ id: 2, title: '제목2', contents: '내용2', isLike: true, type: 'news' },
			{ id: 3, title: '제목3', contents: '내용3', isLike: true, type: 'notice' },
			{ id: 4, title: '제목4', contents: '내용4', isLike: true, type: 'news' },
			{ id: 5, title: '제목5', contents: '내용5', isLike: false, type: 'notice' },
			{ id: 6, title: '제목6', contents: '내용6', isLike: false, type: 'news' },
		]);

		const createPost = newTitle => {
			console.log('createPost');
			console.log('newTitle: ', newTitle);
		};
		return { posts, obj, createPost };
	},
};
</script>

<style lang="scss" scoped></style>
