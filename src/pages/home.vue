<template>
  <f7-page name="home">
    <!-- Top Navbar -->
    <f7-navbar :sliding="false" small>
      Augmented Reality
    </f7-navbar>

    <f7-block class="grid-resizable-demo">
      <f7-row class="align-items-stretch" style="height: 83vh;">
        <homeGridLeft></homeGridLeft>
        <homeGridCenter></homeGridCenter>
        <homeGridRight></homeGridRight>
      </f7-row>
    </f7-block>
  </f7-page>
</template>

<script>
import homeGridLeft from '../pages/Grid/Left/homeGridLeft.vue';
import homeGridCenter from '../pages/Grid/Center/homeGridCenter.vue';
import homeGridRight from '../pages/Grid/Right/homeGridRight.vue';

export default {
name: 'home',
  data () {
    return {}
  },
  components: {
    homeGridLeft: homeGridLeft,
    homeGridCenter: homeGridCenter,
    homeGridRight: homeGridRight
  }
}
</script>