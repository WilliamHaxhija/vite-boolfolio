<script>
export default {
    name: 'ProjectCard',
    props: {
        projectInfo: Object
    }
}
</script>

<template>
    <div class="col-4 my-3">
        <div class="card" style="width: 18rem;">
            <div v-if="projectInfo.cover_image">
                <img :src="`http://127.0.0.1:8000/storage/${projectInfo.cover_image}`" class="card-img-top" :alt="projectInfo.name">
            </div>
            <div v-else>
                <img src="https://picsum.photos/300/200" class="card-img-top" alt="lorem-picsum">
            </div>
            <div class="card-body">
                <h5 class="card-title">{{ projectInfo.name }}</h5>
                <p class="card-text">{{ projectInfo.summary }}</p>
                <router-link :to="{ name: 'single-post', params: { slug: projectInfo.slug } }">Info</router-link>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>