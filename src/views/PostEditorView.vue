<script setup lang="ts">
import { useRoute } from 'vue-router'
import PostEditor from '../components/Post/PostEditor.vue'

const route = useRoute()
</script>

<template>
	<div class="post-detail">
		<PostEditor/>
	</div>
</template>

<style scoped lang="scss">
.post-detail {
	min-height:     100vh;
	display:        flex;
	background:     #f8f9fa;
	flex-direction: row;
}
</style>