<template>
    <div class="flex flex-col gap-6 items-center justify-center" v-if="job">
        <h1 class="font-serif text-2xl font-bold text-violet-600">{{ job.title }}</h1>
        <p class="text-justify px-8 text-lg font-bold">{{ job.details }}</p>
    </div>
    <div class="text-center mt-4" v-else>
        <span class="font-semibold text-lg tracking-wide">Loading job details...</span>
    </div>
</template>

<script>
export default {
    name: "JobDetails",
    data () {
        return {
            job: null
        }
    },
    props: [ "id" ],
    mounted () {
        fetch( `http://localhost:3000/jobs/${ this.id }` )
            .then( res => res.json() )
            .then( data => this.job = data )
            .catch( err => console.log( err.message ) )
    }
}
</script>