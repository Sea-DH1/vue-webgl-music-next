<template>
  <div class="singer" v-loading="!singers.length">
    <index-list :data="singers"></index-list>
  </div>
</template>

<script>
import { getSingerList } from '@/service/singer'
import IndexList from '@/components/base/index-list/index-list'
export default {
  name: 'singer',
  components: {
    IndexList
  },
  data() {
    return { singers: [] }
  },
  async created() {
    const result = await getSingerList()
    this.singers = result.singers
  },
  methods: {}
}
</script>

<style scoped lang="scss" rel="stylesheet/scss">
.singer {
  position: fixed;
  width: 100%;
  top: 88px;
  bottom: 0;
}
</style>
