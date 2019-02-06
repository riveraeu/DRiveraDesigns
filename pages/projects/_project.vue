<template>
  <div class="w-4/5 mx-auto py-16">
    <div class="py-6">
      <p class="heading text-blue text-center py-6">{{ project.title }}</p>
      <div class="body-text text-grey-darker text-center mx-auto lg:w-4/5"> {{ project.text }}</div>
    </div>
    <div class="image-cards">
      <div
        v-for="(image, index) in project.images"
        :key="index"
        class="image-card">
        <VueResponsiveImage
          :image-url="image.src"
          :width-on-screen="30"
          :width-on-screen-tablet="50"
          :width-on-screen-smartphone="75"
          :image-class="'shadow-lg'"
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
