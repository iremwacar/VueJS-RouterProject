<template>
    <div v-if="job">
        <h1>Job Details Page</h1>
        <p>{{ job.title }}</p>
        <p>The jobs id is {{ id}}</p>
        <p>{{ job.details }}</p>
    </div>
  
</template>

<script>
export default {
    props: ['id'],
    data() {
        return{
            job:null
        }
    },
    mounted() {
        fetch('http://localhost:3000/jobs/'+this.id)
      .then((res)=>res.json())
      .then(data => data.job = data)
      .catch(err=>console.log(err.message))
    }
}
</script>

<style>

</style>