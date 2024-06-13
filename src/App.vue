<script>
import { RouterView } from 'vue-router';
import AppHeader from './components/AppHeader.vue';
import ProjectsList from './components/ProjectsList.vue';

export default {
  components: {
    ProjectsList,
    AppHeader
  }
}
</script>

<template>
<AppHeader></AppHeader>
<router-view></router-view>
</template>

<style lang="scss">

</style>
