<template>
    <h1>Jobs</h1>
    <div v-for="job in jobs" :key="job.id">
        <router-link :to="{name: 'jobDetails', params:{id: job.id}}"> <h2>{{ job.title }}</h2></router-link>  
    </div>
</template>

<script>
    export default {
        data(){
            return{
                jobs:[
                    { title: 'UX Designer', id: 1, details: 'I am a UX Designer'},
                    { title: 'Web Developer', id: 2, details: 'I am a Web Developer'},
                    { title: 'Vue Developer', id: 3, details: 'I am a Vue Developer'},
                ]
            }
        }
    }
</script>

<style scoped>

</style>