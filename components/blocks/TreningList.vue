<template>
  <section class="training-list" id="training-list">
    <div class="tl-container">
      <div class="tl-training-types">
        <h4 class="block-subtitle">Виды тренировок</h4>
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
        <ul class="tl-groups">
          <li class="tl-group">
            <div class="age-circle">
              <div class="circle-title">
                от
              </div>
            </div>
            <div class="age-dot">
            </div>
            <div class="age-circle">
              <div class="circle-title">
                до
              </div>
            </div>
          </li>
          <li
            v-for="(group, gr) in group_list"
            :key="`type_${gr}`"
            class="tl-group">
            <div class="age-circle">
              {{group.start_age}}
            </div>
            <div
              v-for="(dot, d) of group.dot_length"
              :key="`type_${d}`"
              class="age-dot">

            </div>
            <div class="age-circle">
              {{group.finish_age}}
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="main-container">
      <div class="left-title">Тренировки</div>
      <div class="right-title right-title__long-mt">Возрастные группы</div>
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
        {start_age:'4', finish_age:'7',   dot_length:3},
        {start_age:'8', finish_age:'13',  dot_length:6},
        {start_age:'14', finish_age:'',   dot_length:12},

        ]
    }
  }
}
</script>
