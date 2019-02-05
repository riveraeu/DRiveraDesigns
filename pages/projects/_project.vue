<template>
  <div class="w-4/5 mx-auto py-16">
    <div class="py-6">
      <p class="heading text-blue text-center py-6">{{ project.title }}</p>
      <div class="body-text text-grey-darker text-center mx-auto w-4/5"> {{ project.text }}</div>
    </div>
    <div class="image-cards">
      <div
        v-for="(image, index) in project.images"
        :key="index"
        class="image-card">
        <VueResponsiveImage
          :image-url="image.src"
          :width-on-screen="50"
          :width-on-screen-tablet="75"
          :width-on-screen-smartphone="100"
          @click.native="openGallery(index)"/>
      </div>
      <LightBox
        ref="lightbox"
        :images="project.images"
        :show-light-box="false"
        :show-thumbs="false"/>
    </div>
  </div>
</template>

<script>
import LightBox from '~/components/lightbox/LightBox.vue'
import VueResponsiveImage from '~/components/ResponsiveImage.vue'

export default {
  components: {
    LightBox,
    VueResponsiveImage
  },
  data() {
    return {
      project: {}
    }
  },
  methods: {
    openGallery(index) {
      this.$refs.lightbox.showImage(index)
    }
  },
  async asyncData({ $axios, params }) {
    try {
      const res = await $axios.$get(`/projects/${params.project}.json`)
      return { project: res }
    } catch (err) {
      throw err
    }
  }
}
</script>

<style scoped>
.image-cards {
  column-count: 3;
  column-gap: 1em;
}
.image-card {
  margin: 0 0 1em;
  width: 100%;
  transition: all 100ms ease-in-out;
  display: inline-block;
  cursor: pointer;
}
.image-card >>> img {
  width: 100%;
}
@media (max-width: 960px) {
  .image-cards {
    column-count: 2;
  }
}
@media (max-width: 600px) {
  .image-cards {
    column-count: 1;
  }
  .image-cards {
    margin: 0 0 0;
  }
}
.card >>> img {
  display: block;
  width: 100%;
}
</style>
