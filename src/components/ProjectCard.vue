<script>
export default {
    name: 'ProjectCard',
    props: {
        projectInfo: Object
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-4 my-3" v-for="project in projectInfo">
                <div  class="card" style="width: 18rem;">
            <!-- <img src="..." class="card-img-top" alt="..."> -->
            <div class="card-body">
                <h5 class="card-title">{{ project.name }}</h5>
                <p class="card-text">{{ project.summary }}</p>
            </div>
        </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>