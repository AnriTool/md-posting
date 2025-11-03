<script lang="ts">
import { marked } from 'marked';
import Post from './Post.vue'

export default {
	components: {
		Post,
	},
	data: () => {
		return {
			input: '',
		}
	},
	computed: {
		markdownData() {
			return marked.parse(this.input);
		},
	},
	methods: {
		update(event) {
			this.input = event.target.value;
		}
	}
}
</script>

<template>
	<article>
		<textarea class="post-editor" :value="input" @input="update"/>
	</article>
	<post
	:text="input"
	/>
</template>
<style lang="scss">
@use "Post";

body {
	max-width: 1600px;
}

.post {
	border: solid black 1px;
	width: 800px;
}

.post-editor {
	width: 800px;
	height: 100%;
}

</style>