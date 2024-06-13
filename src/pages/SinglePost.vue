<script>
import axios from 'axios';
export default {
    name: 'SinglePost',
    data() {
        return {
            project: null
        }
    },
    methods: {
        getSinglePost() {
            axios.get(`http://127.0.0.1:8000/api/projects/${this.$route.params.slug}`)
            .then((response) => {
                this.project = response.data.project;
            });
            
        }
    },
     mounted() {
        this.getSinglePost()
     }
}
</script>

<template>
    <div class="col-4 my-3" v-if="project">
        <div class="card" style="width: 18rem;">
            <div v-if="project.cover_image">
                <img :src="`http://127.0.0.1:8000/storage/${project.cover_image}`" class="card-img-top" :alt="project.name">
            </div>
            <div v-else>
                <img src="https://picsum.photos/300/200" class="card-img-top" alt="lorem-picsum">
            </div>
            <div class="card-body">
                <h5 class="card-title">{{ project.name }}</h5>
                <p class="card-text">{{ project.summary }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>
