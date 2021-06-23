<template>
  <div>
    <BlockNav     />
    <TreningList  />
    <OurTeam      />
    <AboutUs      />
  </div>
</template>
<script>
import BlockNav     from "~/components/blocks/BlockNav";
import TreningList  from "~/components/blocks/TreningList";
import OurTeam      from "~/components/blocks/OurTeam";
import Order        from "~/components/blocks/Order";
import AboutUs      from "~/components/blocks/AboutUs";

// const setBlock = () => {
//   document.getElementById("id").style.display=`block`
// }
// const setNone = () => {
//   document.getElementById("id").style.display=`none`
// }
// document.addEventListener('scroll', (e) => {
//   (window.pageYOffset > window.outerHeight/3  ) ? setBlock() : setNone();
// })


export default {
  layout:'default',
  data () {
    return {
      loading: false,
    }
  },
  components: {
    BlockNav,
    TreningList,
    OurTeam,
    Order,
    AboutUs,
  },


}
</script>

