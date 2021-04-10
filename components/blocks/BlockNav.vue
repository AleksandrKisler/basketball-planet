<template>
  <section class="block-nav" id="block-nav">
    <div class="col-left">
      <div class="nav-item-1-1">
        <h1>Планета <br> баскетбола</h1>
        <img src="~assets/image/block-basketball.svg" class="block-img" alt="aa">
      </div>
      <div class="nav-item-1-2">
        <h1>ЗАПИСЬ НА <br>
          ТРЕНИРОВКУ</h1>
        <img src="~/assets/image/icons/icon-click.svg" alt="click" width="111" height="111">
      </div>
    </div>
    <div class="col-center">
      <div class="nav-row">
        <div class="nav-item-2-1">
          <h2>Наша <br> команда</h2>
          <img src="~/assets/image/icon-team2.svg"  class="block-img" alt="icon-team">

        </div>
        <div class="nav-cross">

        </div>
      </div>
      <div class="nav-item-2-2">
        <h1>ИНФОРМАЦИЯ <br>
          О ТРЕНИРОВКАХ</h1>
        <img src="~assets/image/block-info.svg" class="block-img" alt="aa">
      </div>
      <div class="nav-row">
        <div class="nav-item-h-line"></div>
        <h3>ПЕРВАЯ <br>
          АКАДЕМИЯ СПОРТА <br>
          В ХАНТЫ-МАНСИЙСКЕ
        </h3>
      </div>
    </div>
    <div class="col-right">

    </div>
    <div class="dot"></div>
  </section>
</template>
<script>
export default {
  name: "BlockNav",
  data() {
    return {
      loading: false,
    }
  },

}
</script>

