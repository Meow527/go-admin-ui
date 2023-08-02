<template>
  <BasicLayout>
    <template #wrapper>
      <el-card class="box-card">
        <div v-loading="loading" :style="'height:'+ height">
          <iframe :src="src" frameborder="no" style="width: 100%;height: 100%" scrolling="auto" />
        </div>
      </el-card>
    </template>
  </BasicLayout>
</template>
<script>
export default {
  name: 'Consul',
  components: {
  },
  data() {
    return {
      src: 'http://consul.mzjktech.com/ui/',
      height: document.documentElement.clientHeight - 94.5 + 'px;',
      loading: true
    }
  },
  mounted: function() {
    setTimeout(() => {
      this.loading = false
    }, 230)
    const that = this
    window.onresize = function temp() {
      that.height = document.documentElement.clientHeight - 94.5 + 'px;'
    }
  }
}
</script>
