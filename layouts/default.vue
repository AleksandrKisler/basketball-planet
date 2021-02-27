<template>
  <section class="container">
    <div class="bg-basketball"></div>
    <div class="bg-whistle"></div>
    <div class="bg-basketball-players"></div>
    <div class="bg-card-id"></div>
<!--    <div class="up-to-top" ref="upToTop" v-show="checkHeight">-->
<!--    </div>-->
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
  },
  computed: {
    // checkHeight() {
    //   console.log(this.$refs.upToTop.clientHeight);
    //   return false;
    // }
  }

}
</script>

