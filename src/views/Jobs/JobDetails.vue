<template>
    <div v-if="job">
        <h1>{{job.title}}</h1>
        <p>The job id is {{ id }}</p>
        <p>{{job.details}}</p>      
    </div>
    <div v-else>
        Loading ......
    </div>
</template>

<script>
    export default {
        props: ['id'] ,
        data(){
            return{
                //id: this.$route.params.id
                job: null
            }
        },
        mounted(){
            fetch('http://localhost:3000/jobs/' + this.id)
            .then(response => response.json())
            .then(data => this.job = data)
            .catch(err => console.log(err.message))
        }
    }
</script>

<style scoped>

</style>