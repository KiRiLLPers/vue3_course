<template lang="">
	<div>
		<h3>Список пользователей</h3>
		<post-item
			v-for="post in posts"
			:post="post"
			:key="post.id"
			@remove="removeEmit"
		/>
	</div>
</template>
<script>
import PostItem from '@/components/PostItem';
export default {
	components: { PostItem },
	props: {
		posts: {
			type: Array,
			required: true,
		},
	},
	methods: {
		removeEmit(post) {
			return $emit('remove', post);
		},
	},
};
</script>
<style scoped></style>
