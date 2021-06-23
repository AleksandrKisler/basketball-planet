<template>
  <section class="block-nav" id="block-nav">
    <div class="col-left">
      <div class="nav-item-1-1">
        <h1 class="card-title">Планета <br> баскетбола</h1>
        <img src="~assets/image/block-basketball.svg" class="block-img" alt="aa">
      </div>
      <div class="nav-item-1-2">
        <h1 class="card-title">Запись на <br>
          тренировку</h1>
        <img src="~/assets/image/icons/icon-click.svg" alt="click" width="111" height="111">
      </div>
    </div>
    <div class="col-right">
      <div class="nav-item-2-1">
        <h1 class="card-title">Наша <br> команда</h1>
        <img src="~/assets/image/icon-team2.svg" class="block-img" alt="icon-team">
      </div>
      <div class="nav-item-2-2">
        <h1 class="card-title">Информация <br>
          о тренировках</h1>
        <img src="~assets/image/block-info.svg" class="block-img" alt="aa">
      </div>
    </div>
    <div class="container-border">
      ПЕРВАЯ <br>
      АКАДЕМИЯ СПОРТА <br>
      В ХАНТЫ-МАНСИЙСКЕ
    </div>
    <div class="container-cross"></div>
    <div class="container-border-sm"></div>
    <div class="container-logo">
      <img src="~/assets/image/pb-logo.png" alt="sss" width="110">
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

