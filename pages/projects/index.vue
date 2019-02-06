<template>
  <section class="w-4/5 mx-auto py-16">
    <div class="py-6">
      <h1 class="heading text-blue text-center py-6">Projects</h1>
      <p class="body-text text-grey-darker text-center lg:w-1/2 mx-auto">Take a look at some of the fabulous projects David has worked on. From major remodels to individual rooms, David has done it all.
        See something you like? Dont wait, get in contact with david today to start your own dream project.
      </p>
    </div>
    <div class="image-cards">
      <overlay
        v-for="(project, index) in gallery"
        :key="index"
        :project="project"
        class="image-card"/>
    </div>
  </section>
</template>

<script>
import overlay from '~/components/image-overlay.vue'
import content from '~/assets/content/gallery.json'

export default {
  components: {
    overlay
  },
  data() {
    return {
      gallery: content
    }
  }
}
</script>
