<template>
    <transition :name="popupTransition">
        <div  :class="b([position,{fullscreen}])"  v-show="value">
            <slot></slot>
        </div>
    </transition>
</template>
<script>
import createBasic from 'oreo-ui/components/utils/create-basic'
import Mask from 'oreo-ui/components/mixins/mask'
export default createBasic({
  name: 'popup',
  mixins: [Mask],

  props: {
    overlay: {
      type: Boolean,
      default: true
    },
    closeOverlayByClick: {
      type: Boolean,
      default: true
    },
    fullscreen: {
      type: Boolean,
      default: false
    },
    transition: String,
    position: {
      type: String,
      default: ''
    },
    getContainer: {
      type: Function
      // default: () => document.body
    }
  },
  computed: {
    popupTransition() {
      return this.transition || (this.position === '' ? 'oreo-fade' : `oreo-popup-slide_${this.position}`)
    }
  },
  mounted() {
  },
  beforeDestroy() {
  }
})
</script>
