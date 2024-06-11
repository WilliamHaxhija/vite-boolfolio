<script>
import ProjectsList from './components/ProjectsList.vue';

export default {
  components: {
    ProjectsList
  }
}
</script>

<template>
<h1>Header</h1>
<ProjectsList></ProjectsList>
</template>

<style lang="scss">
@use './style/generic';
</style>
