<template>
  <div>
    <VideoPlayer />
    <AudioPlayer :sources="audioSources" :loop="true" :autoplay="false" />
  </div>
</template>

<script>
import VideoPlayer from '~/components/VideoPlayer'
import AudioPlayer from '~/components/AudioPlayer'

export default {
  components: {
    VideoPlayer,
    AudioPlayer
  },
  data() {
    return {
      audioSources: [
        require('~/assets/audio/my-brightest-diamond-i-have-never-loved-someone.mp3')
      ]
    }
  },
  computed: {},
  mounted() {},
  methods: {}
}
</script>

<style></style>
