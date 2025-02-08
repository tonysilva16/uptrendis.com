<script setup lang="ts">
useHead({
	bodyAttrs: {
		class: 'min-h-screen bg-white selection:bg-primary/10 selection:text-primary dark:bg-gray-900',
	},
});
</script>
<template>
	<div>
		<AppHeader />
		<slot />
		<AppFooter />
	</div>
</template>
