<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<p>{{ hasLectures }}</p>
		<p>{{ hasLectures }}</p>
		<p>{{ existLectures() }}</p>
		<p>{{ existLectures() }}</p>
		<button @click="counter++">Counter : {{ counter }}</button>

		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLectures = computed(() => {
			console.log('computed');
			return teacher.lectures.length > 0 ? '있음 😀' : '없음 🥲';
		});

		const existLectures = () => {
			console.log('method');
			return teacher.lectures.length > 0 ? '있음 😀' : '없음 🥲';
		};

		const counter = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');

		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});

		console.log('Console 출력: ', fullName.value);
		fullName.value = '짐 코딩';

		return {
			teacher,
			hasLectures,
			existLectures,
			counter,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
