<template>
  <section class="container mx-auto py-16">
    <h1 class="heading text-blue text-center py-10">About</h1>
    <div class="body-text text-grey-darker about flex flex-row">
      <VueResponsiveImage
        :image-url="'/about/aboutPicture.jpeg'"
        :width-on-screen="100"
        :width-on-screen-tablet="25"
        :image-class="'shadow-lg'" />
      <div class="px-6">
        <p>David first discovered his passion for design as a young man growing up in Los Angeles.
        He had a strong interest in designing automobiles, which turned to furniture- ultimately designing and producing a line of furniture that sold through the major design centers in America.</p>
        <p>David’s love for art and his practical nature moved him to the world of Interior design and Architecture.
        He studied Industrial Design at Parsons School of Design in New York City and has a degree in Architectural Interiors.</p>
        <p>David has worked as an Interior designer for more than 30 years garnering the highest professional affiliations with the American Society of Interior Designers (ASID),
        the California Council for Interior Design Certification (CCIDC), the National Council for Interior Design Qualification (NCIDQ), and is a Certified Green Building Professional (Build it Green).</p>
        <p>For more than 30 years David Rivera Designs has worked at producing timeless interiors for a broad range of clients in Northern and Southern California. </p>
        <div class="logos mx-auto">
          <a href="https://www.asid.org/"><img src="/about/asid.png" alt="asid logo"></a>
          <a href="https://www.builditgreen.org/"><img src="/about/build-it-green.png" alt="build it green logo"></a>
          <a href="https://ccidc.org/"><img src="/about/ccidc.jpg" alt="ccidc logo"></a>
          <a href="https://www.cidq.org/"><img src="/about/cidq.jpg" alt="cidq.jpg"></a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import VueResponsiveImage from '~/components/ResponsiveImage.vue'

export default {
  components: {
    VueResponsiveImage
  }
}
</script>

<style scoped>
  @tailwind preflight;
  .about {
    height: 70vh;
  }
  .about >>> p {
    @apply py-2
  }
  .logos >>> img {
    @apply w-1/5 px-4
  }

  @tailwind utilities;
</style>
