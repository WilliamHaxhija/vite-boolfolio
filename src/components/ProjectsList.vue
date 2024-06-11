<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default {
    name: 'ProjectsList',
    components: {
        ProjectCard
    },
    data() {
        return {
            projects: null
        }
    },
    methods: {
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects')
            .then((response) => {
                this.projects = response.data.results;
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
<ProjectCard :projectInfo="projects"></ProjectCard>
</template>

<style scoped lang="scss">

</style>