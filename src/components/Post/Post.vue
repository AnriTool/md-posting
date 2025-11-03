<script lang="ts">
import { marked } from 'marked';

export default {
	data: () => {
		return {
			markdownData: '',
		}
	},
	props: {
		postPath: String,
		text:     String
	},
	async mounted() {

		let text: string;
		if (this.postPath) {
			const postResponse = await fetch(`${import.meta.env.BASE_URL}/posts/${this.postPath}/${this.postPath}.md`);
			text = await postResponse.text();
		}
		else {
			text = this.text
		}

		// Override function
		const renderer = {
			image({ href, title, text, tokens }) {
				let tag = 'img';

				if (href.includes('.mp4')) {
					tag = 'video'
				}

				return `
			<figure>
				<${tag} src="${import.meta.env.BASE_URL}${href}" alt="${text}" controls="controls"> </${tag}>
				<figcaption>${text}</figcaption>
			</figure>
		`;
			}
		};

		marked.use({ renderer });

		this.markdownData = marked.parse(text);
	},
	computed: {
	},
	watch: {
		text(value) {
			this.markdownData = marked.parse(value);
		}
	}
}
</script>

<template>
	<article class="post">
		<div class="post-content">
			<div v-html="markdownData"/>
		</div>
	</article>
</template>
<style lang="scss">
@use "Post";
</style>