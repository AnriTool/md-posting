<script setup lang="ts">
defineProps<{
}>()
</script>

<template>
	<div class="nav-header">
		This is Header
		<slot/>
	</div>
</template>

<style lang="scss">
@use "NavigationHeader";
</style>
