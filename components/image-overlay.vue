<template>
  <div
    class="relative"
    @mouseover="active = true"
    @mouseleave="active = false">
    <nuxt-link :to="{path: '/projects/'+project.slug, params: {slug: project.slug}}">
      <VueResponsiveImage
        :image-url="project.url"
        :alt="project.slug"
        :width-on-screen="30"
        :width-on-screen-tablet="50"
        :width-on-screen-smartphone="75"
        :image-class="'shadow-lg'"
      />
      <div
        v-show="active"
        class="image-overlay">
        <h3 class="text-white image-title text-3xl"> {{ project.title }}</h3>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
import VueResponsiveImage from '~/components/ResponsiveImage.vue'

export default {
  components: {
    VueResponsiveImage
  },
  props: {
    project: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      active: false
    }
  }
}
</script>

<style>
  .image-overlay {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background-color: rgba(38, 50, 56, 0.7);
    display: table;
  }
  .image-title {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
  }
</style>
