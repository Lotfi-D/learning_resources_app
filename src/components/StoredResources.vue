<template>
    <ul>
        <learning-resource v-for="learningResource in resources" :key="learningResource.id"
            :title="learningResource.title" 
            :description="learningResource.description" 
            :link="learningResource.link">
        </learning-resource>
    </ul>
</template>

<script>
import LearningResource from './LearningResource';

export default {
    inject: ['resources'],
    components:{
        LearningResource
        },
    data() {

    },
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>