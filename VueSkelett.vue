<script>
export default {
  name: 'VueSkelett',
  props: {
    type: {
      type: String,
      default: 'flat',
      validator: function(value) {
        return ['circle', 'flat'].indexOf(value) !== -1
      }
    },
    width: {
      type: [Number, String]
    },
    height: {
      type: [Number, String]
    },
    size: {
      type: [Number, String]
    },
    radius: {
      type: [Number, String],
      default: 0
    }
  },
  data() {
    return {
      isPercentRegex: new RegExp('%')
    }
  },
  computed: {
    widthRegex() {
      return this.isPercentRegex.test(this.width) ? `${this.width}` : `${this.width}px`
    },
    heightRegex() {
      return this.isPercentRegex.test(this.height) ? `${this.height}` : `${this.height}px`
    },
    sizeRegex() {
      return this.isPercentRegex.test(this.size) ? `${this.size}` : `${this.size}px`
    },
    radiusRegex() {
      return this.isPercentRegex.test(this.radius) ? `${this.radius}` : `${this.radius}px`
    },
    sizeStyle() {
      return {
        width: this.size ? this.sizeRegex : this.widthRegex,
        height: this.size ? this.sizeRegex : this.heightRegex
      }
    },
    borderRadiusStyle() {
      return {
        borderRadius: this.radiusRegex
      }
    }
  }
}
</script>

<template lang="pug">
  .v-skelett-circle(v-if="type === 'circle'" :style="sizeStyle")
  .v-skelett-flat(v-else :style="[sizeStyle, borderRadiusStyle]")
</template>

<style lang="scss" scoped>
.v-skelett-circle {
  border-radius: 50%;
  animation: pulse 1s infinite;
}

.v-skelett-flat {
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0% {
    background-color: #ddd;
  }
  50% {
    background-color: #d0d0d0;
  }
  100% {
    background-color: #ddd;
  }
}
</style>
