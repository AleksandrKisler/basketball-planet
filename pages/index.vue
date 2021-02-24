<template>
  <div>
    <BlockNav     />
    <TreningList  />
    <OurTeam      />
    <Order        />
    <AboutUs      />
  </div>
</template>
<script>
import BlockNav     from "~/components/blocks/BlockNav";
import TreningList  from "~/components/blocks/TreningList";
import OurTeam      from "~/components/blocks/OurTeam";
import Order        from "~/components/blocks/Order";
import AboutUs      from "~/components/blocks/AboutUs";

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

