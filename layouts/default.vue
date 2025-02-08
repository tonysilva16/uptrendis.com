<script setup lang="ts">
const { setup } = useTheme();
useHead({
    bodyAttrs: {
        class: "min-h-screen bg-white selection:bg-primary/10 selection:text-primary dark:bg-gray-900",
    },
});

onMounted(() => {
    setup();
});
</script>
<template>
    <div>
        <AppHeader />
        <slot />
        <AppFooter />
    </div>
</template>
