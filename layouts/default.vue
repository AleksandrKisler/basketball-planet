<template>
  <section class="container">
    <div class="bg-basketball"></div>
    <div class="bg-whistle"></div>
    <Header />
    <div class="main">
      <Nuxt />
    </div>
    <Footer />
  </section>

</template>s
<script>
import Header from "~/components/basic/Header";
import Footer from "~/components/basic/Footer";
export default {
  head: {
    title: 'Планета Баскетбола',
  },
  components: {
    Header,
    Footer
  }

}
</script>

