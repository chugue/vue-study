<template>
	<div></div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
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
