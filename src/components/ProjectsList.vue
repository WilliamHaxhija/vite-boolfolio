<script>
import axios from 'axios';

export default {
    name: 'ProjectsList',
    data() {
        return {
            projects: null
        }
    },
    methods: {
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects')
            .then((response) => {
                console.log(response.data.results);
                // this.projects = 
            });
        }
    },
    mounted() {
        this.getProjects();
    }
}
</script>

<template>
<h3>Projects List</h3>
</template>

<style scoped lang="scss">

</style>