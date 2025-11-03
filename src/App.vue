<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import NavigationHeader from './components/NavigationHeader/NavigationHeader.vue'
</script>

<template>
	<header>
		<div class="wrapper">
<!--			<navigation-header>-->
<!--				<nav>-->
<!--					<RouterLink to="/">Home</RouterLink>-->
<!--					<RouterLink to="/about">About</RouterLink>-->
<!--				</nav>-->
<!--			</navigation-header>-->
		</div>
	</header>

	<RouterView />
</template>

<style lang="scss">
@use "App";
</style>
