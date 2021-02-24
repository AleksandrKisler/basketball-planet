<template>
  <section class="training-list" id="training-list">
    <div class="tl-container">
      <div class="tl-training-types">
        <h4>Виды тренировок</h4>
        <ul class="tl-types">
          <li
            v-for="(type, tp) in types_list"
            :key="`type_${tp}`"
            class="tl-type"
            :style="{ 'background-image': 'url('+require(`~/assets/image/icons/training-types/${type.bg}`) +')'}">
            <img
              :src="require(`~/assets/image/icons/training-icons/${type.icon}`)"
              :alt="type.type_name"
              width="60"
              class="tl-img"
            >
            <p class="tl-type-name">{{type.type_name}}</p>
          </li>
        </ul>
      </div>
      <div class="tl-age-groups">
        <h4>Возрастные группы</h4>
        <ul class="tl-groups">
          <li
            v-for="(group, gr) in group_list"
            :key="`type_${gr}`"
            class="tl-group">
            <div class="tl-dot"></div>
            {{group.age}}
          </li>
        </ul>
      </div>
    </div>
    <div class="tl-line">
      <h3>Тренировки</h3>
      <div class="line"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: "TreningList",
  data () {
    return {
      loading:false,
      types_list: [
        {bg: 'trening_1.png', icon: 'basketball_1.svg', type_name: 'Индивидуальные тренировки'},
        {bg: 'trening_2.png', icon: 'basketball_2.svg', type_name: 'Обще-возрастные тренировки'},
        {bg: 'trening_3.png', icon: 'basketball_3.svg', type_name: 'Индивидуальные тренировки'},
                  ],
      group_list: [
        {age:' От 4 до 7 лет'},
        {age:' От 8 до 13 лет'},
        {age:' От 14+'},
        ]
    }
  }
}
</script>
