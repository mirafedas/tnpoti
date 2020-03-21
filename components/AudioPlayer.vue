<template>
  <div @click="isMuted = !isMuted">
    <button
      :class="['mute-btn', isMuted ? 'unmuted' : 'muted']"
      @click="togglePlayback"
    ></button>
  </div>
</template>

<script>
import VueHowler from 'vue-howler'

export default {
  mixins: [VueHowler],
  data: () => {
    return {
      isMuted: false
    }
  },
  methods: {
    // togglePlayback() {
    //   this.isMuted = !this.isMuted
    // }
  }
}
</script>

<style lang="scss" scoped>
.mute-btn {
  z-index: 100;
  position: absolute;
  top: 30px;
  right: 30px;
  height: 30px;
  width: 30px;
  border: none;
  background-color: white;
  border-radius: 30px;
}

.muted {
  background-image: url('~assets/icons/on.png');
  background-size: contain;
}

.unmuted {
  background-image: url('~assets/icons/off.png');
  background-size: contain;
}
</style>
