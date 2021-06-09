<template>
<section class="order" id="order">
  <div class="o-container">
    <div class="o-info">
      <h3>Первая тренировка</h3>
      <p>Бесплатно</p>
      <h4>tel. <a href="tel:+7(992) 330-90-07"  type="phone">+7(992) 330-90-07</a></h4>
    </div>
    <div class="o-container-line"></div>
    <div class="o-order-form">
      <div class="o-form-title">
        Начать запись
      </div>
      <div class="o-form-body" @click="modal.show=true">
        <img src="~/assets/image/icons/icon-click.svg" alt="click">
      </div>
    </div>
  </div>
  <div class="o-line">
    <h3>Записаться</h3>
    <div class="line"></div>
  </div>
  <tm-modal :visible.sync="modal.show"  width="450" marginTop="100px">
    <template v-slot:body>
      <h3>Запись через сайт временно не доступна</h3>
      <p>Вы можете оформить запись через группу <a href="https://vk.com/basketballplanet?w=app6094020_-184295420">Вконтакте</a></p>
    </template>
    <template v-slot:footer>
      <button class="modal-button" @click="modal.show=false" :disabled="modal.loading">Закрыть</button>
    </template>
  </tm-modal>
</section>
</template>

<script>
import Modal from "~/components/Modal";
export default {
  name: "Order",
  data() {
    return {
      modal: {
        show: false
      }
    }
  },
  components: {
    'tm-modal':Modal,
  }
}
</script>

