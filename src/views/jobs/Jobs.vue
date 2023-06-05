<template>
    <div class="flex flex-col gap-6">
        <h1 class="font-serif text-2xl self-center font-bold text-rose-600">Jobs</h1>
        <div class="flex flex-row gap-3 items-center justify-center font-semibold" v-if="jobs.length">
            <div v-for="job in jobs" :key="job.id" class="bg-slate-200 p-5 rounded-lg hover:bg-slate-400">
                <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
                    <h2>{{ job.title }}</h2>
                </router-link>
            </div>
        </div>
        <div class="text-center mt-4" v-else>
            <span class="font-semibold text-lg tracking-wide">Loading jobs...</span>
        </div>
    </div>
</template>

<script>
export default {
    name: "Jobs",
    data () {
        return {
            jobs: []
        }
    },
    mounted () {
        fetch( "http://localhost:3000/jobs" )
            .then( res => res.json() )
            .then( data => this.jobs = data )
            .catch( err => console.log( err.message ) )
    }
};
</script>