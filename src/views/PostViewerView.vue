<script setup lang="ts">
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import Post from '../components/Post/Post.vue'

const route = useRoute()
const postSlug = computed(() => route.params.slug)
</script>

<template>
	<div class="post-detail">
		<Post v-if="postSlug" :post-path="postSlug" />
<!--		<div class="navigation">-->
<!--			<router-link to="/" class="back-link"><- Назад</router-link>-->
<!--		</div>-->
	</div>
</template>

<style scoped lang="scss">
.post-detail {
	min-height: 100vh;
	background: #f8f9fa;
}

.loading {
	text-align: center;
	padding: 2rem;
	color: #7f8c8d;
}

.navigation {
	max-width: 800px;
	margin: 0 auto;
	padding: 2rem;
}

.back-link {
	color: #4fa2dc;
	text-decoration: none;
	font-weight: 500;
}

.back-link:hover {
	text-decoration: underline;
}
</style>