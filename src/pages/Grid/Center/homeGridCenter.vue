<template>
  <f7-col resizable class="display-flex flex-direction-column" style="padding: 0px; border: none; min-width: 55%; width:65%; background-color: transparent">
    <homeGridCenterTop resizable></homeGridCenterTop>
    <homeGridCenterBottom></homeGridCenterBottom>
  </f7-col>
</template>

<script>
import homeGridCenterTop from '../Center/Top/homeGridCenterTop';
import homeGridCenterBottom from '../Center/Bottom/homeGridCenterBottom.vue';

export default {
name: 'homeGridCenter',
  data () {
    return {}
  },
  components: {
    homeGridCenterTop: homeGridCenterTop,
    homeGridCenterBottom: homeGridCenterBottom
  }
}
</script>