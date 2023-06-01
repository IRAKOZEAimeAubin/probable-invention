<template>
    <div class="flex flex-col gap-6">
        <h1 class="font-serif text-2xl self-center font-bold text-violet-600">Job Details</h1>
        <p class="text-justify px-8">The job id is: {{ id }}</p>
    </div>
</template>

<script>
export default {
    name: "JobDetails",
    data () {
        return {
            id: this.$route.params.id
        }
    }
}
</script>