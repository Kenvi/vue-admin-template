<template>
  <div class="dashboard-container">
    <jm-editor></jm-editor>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import editor from './editor'
export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  },
  components: {
    'jm-editor': editor
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
