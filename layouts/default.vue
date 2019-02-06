<template>
  <div>
    <Header/>
    <nuxt/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/header'
import Footer from '@/components/footer'

export default {
  components: {
    Header,
    Footer
  }
}
</script>

<style>
  @tailwind preflight;

  html, body {
    font-family: 'Roboto', sans-serif;
  }
  a {
    @apply no-underline
  }
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
  @tailwind utilities;
</style>
