<template>
	<div class="container">
		<h2>班课{{ id }}详情页面</h2>
		<img :src="course.cover">
		<p>{{course.courseName}}</p>
		<p>{{course.courseClass}}</p>
	</div>
</template>

<script>
export default {
	name: 'CourseDetail',
	data() {
		return {
			id: this.$route.params.id,
			course: {}
		};
	},
	created() {
		var _this = this;
		this.$http.get('http://localhost:8080/api/course/' + this.id).then(function(response) {
			_this.course = response.data;
		});
	}
};
</script>
<style scoped></style>