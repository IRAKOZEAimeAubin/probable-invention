<template>
    <div class="flex flex-col items-center justify-center gap-2">
        <h2 class="font-bold font-bebas text-8xl tracking-wide">404</h2>
        <h3 class="font-semibold font-mono text-xl">Page Not Found</h3>
        <router-link :to=" { name: 'Home' } ">
            <span class="text-blue-800 font-extrabold">Take Me Home</span>
        </router-link>
    </div>
</template>

<script>
export default {
    name: "NotFound",
}
</script>