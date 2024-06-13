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
            projects: [],
            currentPage: null,
            nextPageUrl: null
        }
    },
    methods: {
        getProjects(pageNumber) {
            axios.get('http://127.0.0.1:8000/api/projects', {
                params: {
                    page: pageNumber
                }
            })
                .then((response) => {
                    this.projects = response.data.results.data;
                    this.currentPage = response.data.results.current_page;
                    this.nextPageUrl = response.data.results.next_page_url;
                });
        }
    },
    mounted() {
        this.getProjects(this.currentPage);
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <ProjectCard v-for="project in projects" :projectInfo="project" :key="project.id"></ProjectCard>
            <nav class="d-flex justify-content-center">
                <ul class="pagination">
                    <div v-if="currentPage !== 1 && currentPage > 0">
                        <li class="page-item" @click="getProjects(currentPage - 1)"><a class="page-link">Previous Page</a></li>
                    </div>
                    <div v-if="nextPageUrl">
                        <li class="page-item" @click="getProjects(currentPage + 1)"><a class="page-link">Nex Page</a></li>
                    </div>
                </ul>
            </nav>
        </div>
    </div>
</template>

<style scoped lang="scss">
li {
    cursor: pointer;
}
</style>