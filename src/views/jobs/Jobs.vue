<template>
    <div class="flex flex-col gap-6">
        <h1 class="font-serif text-2xl self-center font-bold text-rose-600">Jobs</h1>
        <div class="flex flex-row gap-3 items-center justify-center font-semibold">
            <div v-for="job in jobs" :key="job.id">
                <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
                    <h2>{{ job.title }}</h2>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Jobs",
    data () {
        return {
            jobs: [
                {
                    id: 1,
                    title: "Hokage",
                    details:"Lead the village."
                },
                {
                    id: 2,
                    title: "Anbu",
                    details:"Remove the unwanteds."
                },
                {
                    id: 3,
                    title: "Jonins",
                    details:"Train the young ones."
                },
            ]
        }
    }
};
</script>