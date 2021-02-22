<template>
  <header class="header">
    <nav class="main-menu">
      <a
        v-for="(link,id) in navigation_list"
        :key="`key_${id}`"
        :to="link.to"
        :class="['header-link',{'active': link.active}]"
        @click="setActive(link)"
      >
        {{link.title}}
      </a>
    </nav>
    <nav class="user-bar">
    </nav>
  </header>
</template>
<script>
export default {
  name: 'Header',
  data () {
    return {
      loading: false,
      navigation_list: [
        {id:1,title:'Планета Баскетбола',to:'#', active:true},
        {id:2,title:'О тренировках',to:'#', active:false},
        {id:3,title:'наша команда',to:'#', active:false},
        {id:4,title:'запись',to:'#', active:false},
      ],
    }
  },
  methods: {
    setActive (item){
      for (const nav of this.navigation_list) {
        nav.active = false;
      }
      item.active = true;
    }
  }
}
</script>
