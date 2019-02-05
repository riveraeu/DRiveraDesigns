<template>
  <div>
    <section id="hero-image" class="bg-center bg-cover">
      <div class="text-white py-32 px-8 sm:px-16 w-full sm:w-3/4 lg:w-1/3">
        <h1 class="text-5xl font-bold py-5">David Rivera Designs</h1>
        <p class="text-xl font-medium leading-normal">David Rivera is an Interior Designer and space planner operating in the San Francisco Bay Area. Looking to remodel or start a new project? Work with David to make your vision come to life.</p>
        <a href="/contact"><button class="btn btn-blue my-8 p-4 focus:outline-none">Get Started</button></a>
      </div>
    </section>
    <section id="site-building" class="py-10">
      <div class="flex flex-wrap container mx-auto px-4 text-grey-darker">
        <div class="w-full text-center py-10">
          <h1 class="heading text-blue">Project Overview</h1>
        </div>
        <div class="flex flex-row flex-wrap lg:flex-no-wrap py-8 md:px-8">
          <div class="lg:w-full">
            <h2 class="sub-heading py-2 underline">{{ content.planning.title }}</h2>
            <p class="body-text lg:pr-6 pb-4">{{ content.planning.text }}</p>
          </div>
          <VueResponsiveImage
            :image-url="content.planning.url"
            :image-ratio="1916/1520"
            :width-on-screen="50"
            :width-on-screen-tablet="75"
            :width-on-screen-mobile="100"
            :image-class="'shadow-lg'" />
        </div>
        <div class="flex flex-row flex-wrap lg:flex-no-wrap py-8 md:px-8">
          <VueResponsiveImage
            :image-url="content.construction.url"
            :width-on-screen="10"
            :width-on-screen-tablet="75"
            :width-on-screen-mobile="100"
            :image-class="'shadow-lg'" />
          <div class="lg:w-full lg:py-16 lg:pl-6">
            <h2 class="sub-heading py-2 underline text-grey-darker">{{ content.construction.title }}</h2>
            <p class="body-text">{{ content.construction.text }}</p>
          </div>
        </div>
        <div class="flex flex-row flex-wrap lg:flex-no-wrap py-8 md:px-8">
          <div class="lg:w-full lg:py-16 lg:pr-6">
            <h2 class="sub-heading py-2 underline text-grey-darker">{{ content.completion.title }}</h2>
            <p class="body-text pb-4">{{ content.completion.text }}</p>
          </div>
          <VueResponsiveImage
            :image-url="content.completion.url"
            :width-on-screen="10"
            :width-on-screen-tablet="75"
            :width-on-screen-mobile="100"
            :image-class="'shadow-lg'" />
        </div>
      </div>
    </section>
    <section class="bg-grey-lighter pb-2 text-grey-darkest">
      <div class="container mx-auto ">
        <div class="pt-8 px-4 text-center w-full md:w-2/3 mx-auto">
          <h1 class="heading py-2">Contact</h1>
          <p class="text-xl font-medium leading-normal">Ready to get started on your dream project? Get in touch with David today to set up a meeting and get the ball rolling.</p>
          <a href="/contact"><button class="btn btn-blue focus:outline-none">Get Started</button></a>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import VueResponsiveImage from '~/components/ResponsiveImage.vue'
import process from '~/assets/content/process.json'

export default {
  components: {
    VueResponsiveImage
  },
  data() {
    return {
      content: process
    }
  }
}
</script>

<style>
  #hero-image {
    height: 90vh;
    background-image: url("https://res.cloudinary.com/rivera-web-solutions/image/upload/b_black,o_60/v1549053311/DRiveraDesigns/Mill%20Valley/main-min.jpg");
  }
</style>
