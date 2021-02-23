<template>
  <footer class="footer">
    <div class="reference-information">
      <div class="helpful-item">
        <h4>Социальные сети</h4>
        <div class="icon-list">
          <a
            v-for="(icon, ic) in icon_list"
            :key="`ic_${ic}`"
            :href="icon.href"
          ><img
            :src="require(`~/assets/image/icons${icon.src}`)"
            :alt="icon.alt"
            class="icon-link"
            width="24"

          ></a>
        </div>
      </div>
      <div class="footer-logo">
        <img src="~/assets/image/pb-logo.png" width="88" height="78" alt="footer-logo">
        <h2>Планета <br> Баскетбола</h2>
      </div>
      <div class="helpful-item">
        <h4>кОНТАКТЫ</h4>
        <div class="phone-list">
          <a
            v-for="(phone, ip) in phone_list"
            :key="`index_${ip}`"
            :href="'tel:' + phone.phone" >Тел: {{phone.phone}}</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      loading: false,
      icon_list:[
        {href:'#', src:'/facebook.svg', alt:'social network vk'},
        {href:'#', src:'/instagram.svg', alt:'social network instagram'},
        {href:'#', src:'/vk.svg', alt:'social network facebook'},
      ],
      phone_list:[
        {phone:'+7(495) 666-01-66'},
        {phone: '+7(495) 666-01-96'}
      ],
    }
  },

}
</script>


