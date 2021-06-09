<template>
  <div :class="['tm-dimmer active']" v-if="visible" :style="{position: 'fixed'}">
    <div :class="['tm-modal', 'attached', attached]" ref="modal" :style="mstyle">
      <span v-if="closeButton" aria-hidden="true" class="modal-close" @click="closeHandler">&times;</span>
      <template v-if="!noHeader">
        <header :class="{'hidden': customHeader}" class="modal-header">
          <slot name="header"></slot>
        </header>
      </template>

      <div :class="{'custom-modal-body': true, 'hidden': !customBody}">
        <slot name="custom-body"></slot>
      </div>
      <div :class="{'hidden': customBody}" class="modal-body">
        <slot name="body"></slot>
      </div>

      <footer class="modal-footer">
        <slot name="footer"></slot>
      </footer>
    </div>
  </div>
</template>
<script>
export default {
  name: 'tm-modal',
  props: {
    customHeader: {type: Boolean, default: false},
    noHeader: {type: Boolean, default: false},    // Иногда нужно вообще спрятать хедер
    customBody: {type: Boolean, default: false},
    title: { type: String },
    attached: { type: String, default: 'center' },
    padding: { type: String, default: '1em' },
    visible: { type: Boolean, default: false },
    closeButton: { type: Boolean, default: false }, // Кнопка закрытия окна
    marginTop: { type: String, default: '100px' },
    width: { type: [Number, String], default: 850 },
    height: { type: [Number, String], default: 500 },
    triggerEvent: { type: Event, default: null },
    dynamicWidth: { type:Boolean, default:false },
  },
  data () {
    return {
      left: '50%',
      top: '0px',
      marginLeft: this.width / 2,
      marginTopV: this.marginTop
    }
  },
  computed: {
    mstyle () {
      const { attached, width, height } = this
      if (attached === 'center') {
        const { left, top } = this
        if (this.dynamicWidth) {
          return {
            'margin-top': this.marginTopV,
            'margin-left': `-${this.marginLeft*1.35}px`,
            left,
            top
          }
        }
        return {
          'margin-top': this.marginTopV,
          'width': `${this.width}px`,
          'margin-left': `-${this.marginLeft}px`,
          left,
          top
        }
      } else if (attached === 'left' || attached === 'right') {
        return { width }
      } else {
        return { height }
      }
    }
  },
  watch: {
    visible: function (val) {
      // Kostyl productions present
      document.body.style.overflow = (val) ? "hidden" : "";
      document.body.style.paddingRight = (val) ? "15px" : "0";
    },
    triggerEvent (nowVal, oldVal) {
      if (this.attached === 'center') {
        if (nowVal != null) {
          this.calLeftTop(nowVal)
          this.marginLeft = 0
          this.marginTopV = '0px'
        } else {
          this.left = '50%'
          this.top = '0px'
          this.marginLeft = this.width / 2
          this.marginTopV = this.marginTop
        }
      }
    }
  },
  methods: {
    closeHandler () {
      this.$emit('update:visible', false)
    },
    calLeftTop (event) {
      const { target } = event
      const {width, left, top} = getTargetOffset(target)
      this.left = `${left + width + 10}px`
      this.top = `${top}px`
    }
  }
}

const getTargetOffset = (target) => {
  let { offsetWidth, offsetHeight, offsetLeft, offsetTop } = target
  if (target.offsetParent != null) {
    const {left, top} = getTargetOffset(target.offsetParent)
    offsetLeft += left
    offsetTop += top
  }
  return {height: offsetHeight, width: offsetWidth, left: offsetLeft, top: offsetTop}
}
</script>
