<template>
    <canvas :bind="attrs" ref="VueImageCrop"></canvas>
</template>
<script>

  export default {
    name: 'vue-img-crop',
    props: {
      image: {
        type: String,
        required: true
      }
      resultImage: {
        type: String,
        required: true
      },
      changeOnFly: {
        type: Boolean,
        default: false
      },
      areaType: {
        type: String,
        default: 'circle'
      },
      areaMinSize: {
        type: Number,
        default: 80
      },
      resultImageSize: {
        type: Number,
        default: 200
      },
      resultImageFormat: {
        type: String,
        default: 'image/png'
      },
      resultImageQuality: Number
    },
    data () {
      let attrs = {
        ...this.$props
      }
      return { attrs }
    }
  }
</script>
<style lang="less" scoped>
img-crop {
  width:100%;
  height:100%;
  display:block;
  position:relative;
  overflow:hidden;
  canvas {
    display:block;
    position:absolute;
    top:50%;
    left:50%;

    // Disable Outline
    outline: none;
    -webkit-tap-highlight-color: rgba(255, 255, 255, 0); /* mobile webkit */
  }
}
</style>
