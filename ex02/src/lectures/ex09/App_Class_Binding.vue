<template>
	<div>
		<div class="text" :class="[isActive ? 'active-class' : 'class', ErrorClass]">
			텍스트 입니다.
		</div>
		<button @click="toggle">toggle</button>
		<button @click="hasError = !hasError">toggle Error</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);

		const toggle = () => {
			isActive.value = !isActive.value;
		};
		const hasError = ref(true);

		const ClassObject = computed(() => {
			return {
				active: true,
				'text-danger': true,
			};
		});

		const ActiveClass = ref('active');
		const ErrorClass = ref('error');

		return {
			toggle,
			isActive,
			hasError,
			ClassObject,
			ActiveClass,
			ErrorClass,
		};
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
	font-size: 50px;
}
.text-danger {
	color: red;
}
</style>
