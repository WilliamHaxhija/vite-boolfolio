<script>
export default {
    name: 'ProjectCard',
    props: {
        projectInfo: Array
    },
    printableImage: '',
    methods: {
        getPrintableImageString(image) {
            if (image) {
                this.printableImage = image.substr( 16, image.length - 1 );
                return this.printableImage;
            } else {
                return 'No Image'
            }
        }
    }
}
</script>

<template>
    <div class="col-4 my-3">
        <div class="card" style="width: 18rem;">
            <img :src="getPrintableImageString(projectInfo.cover_image)" class="card-img-top" :alt="projectInfo.name">
            <div class="card-body">
                <h5 class="card-title">{{ projectInfo.name }}</h5>
                <p class="card-text">{{ projectInfo.summary }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>