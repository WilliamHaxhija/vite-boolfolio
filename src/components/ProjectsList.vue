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
            projects: []
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
    <div class="container">
        <div class="row">
            <h3>Projects List</h3>
            <ProjectCard v-for="project in projects" :projectInfo="project" :key="project.id"></ProjectCard>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>