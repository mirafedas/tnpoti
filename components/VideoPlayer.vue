<template>
  <video-player
    ref="videoPlayer"
    class="video-player-box"
    :options="playerOptions"
    :playsinline="true"
    :play-on-load-start="true"
    custom-event-name="customstatechangedeventname"
    @pause="changeVideo"
    @ready="playerReadied"
  >
  </video-player>
</template>

<script>
import '~/assets/video/1.webm'

export default {
  data() {
    return {
      counter: 1,
      playerOptions: {
        muted: true,
        width: '100vw',
        height: '100vh',
        language: 'en',
        playbackRates: [0.7, 1.0, 1.5, 2.0],
        sources: [
          {
            type: 'video/mp4',
            src: '_nuxt/assets/video/2.webm'
          }
        ],
        poster:
          'https://images.unsplash.com/photo-1561447157-3e2d9b9a698b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1352&q=80'
      }
    }
  },
  computed: {
    player() {
      return this.$refs.videoPlayer.player
    }
  },
  mounted() {
    console.log('this is current player instance object', this.player)
  },
  methods: {
    // listen event
    onPlayerPlay(player) {
      console.log('player play!', player)
    },
    onPlayerPause(player) {
      console.log('player pause!', player)
    },
    // ...player event

    // or listen state event
    playerStateChanged(playerCurrentState) {
      console.log('player current update state', playerCurrentState)
    },

    // player is ready
    playerReadied(player) {
      console.log(this.playerOptions.sources)
      // you can use it to do something...
      // player.[methods]
    },
    changeVideo() {
      this.playerOptions.sources[0].src = `_nuxt/assets/video/${this.counter +
        1}.webm`
      console.log(this.playerOptions.sources[0].src)
    }
  }
}
</script>

<style>
.video-player-box .video-js {
  width: 100vw;
  height: 100vh;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.video-js .vjs-big-play-button {
  top: 50%;
  left: 50%;
  transform: translateX(-50%);
}
</style>
