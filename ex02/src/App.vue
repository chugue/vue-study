<template>
	<div>
		<TheNav></TheNav>
		<TheView></TheView>
	</div>
</template>

<script>
import TheNav from './components/TheNav.vue';
import TheView from './components/TheView.vue';

export default {
	components: {
		TheNav,
		TheView,
	},
	setup() {
		const message = ref('');

		watch(message, (newValue, oldValue) => {
			//DOM
			//API
			//state 변경

			console.log('NewValue: ', newValue);
			console.log('OldValue: ', oldValue);
		});
		return { message };
	},
};
</script>

<style lang="scss" scoped></style>
