<template>
  <transition name="el-loading-fade" @after-leave="handleAfterLeave">
    <div
      v-show="visible"
      class="el-loading-mask hwc-loading-mask"
      :style="{ backgroundColor: background || '' }"
      :class="[customClass, { 'is-fullscreen': fullscreen }]">
      <div class="el-loading-spinner hwc-loader-spinner">
        <!--<svg v-if="!spinner" class="circular" viewBox="25 25 50 50">
          <circle class="path" cx="50" cy="50" r="20" fill="none"/>
        </svg>-->
<!--        <div v-if="!spinner" class="hwc-spinner">-->
<!--        </div>-->
<!--        <i v-else :class="spinner"></i>-->
<!--        <p v-if="text" class="el-loading-text">{{ text }}</p>-->
        <h1>ЗАГРУЗКА...</h1>
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
  </transition>
</template>

<script>
  export default {
    data() {
      return {
        text: null,
        spinner: null,
        background: null,
        fullscreen: true,
        visible: false,
        customClass: ''
      };
    },

    methods: {
      handleAfterLeave() {
        this.$emit('after-leave');
      },
      setText(text) {
        this.text = text;
      }
    }
  };
</script>
