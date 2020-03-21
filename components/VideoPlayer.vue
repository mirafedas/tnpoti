<template>
  <video-player
    ref="videoPlayer"
    class="video-player-box"
    :options="playerOptions"
    :playsinline="true"
    :play-on-load-start="true"
    :oncanplay="muteVideo"
    @ended="changeVideo"
  >
  </video-player>
</template>

<script>
export default {
  data() {
    return {
      counter: 1,
      playerOptions: {
        muted: true,
        width: '100vw',
        height: '100vh',
        language: 'en',
        autoplay: true,
        playbackRates: [0.7, 1.0, 1.5, 2.0],
        sources: [
          {
            type: 'video/mp4',
            src: require('assets/video/1.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/2.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/3.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/4.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/5.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/6.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/7.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/8.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/9.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/10.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/11.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/12.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/13.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/14.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/15.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/16.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/17.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/18.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/19.webm')
          },
          {
            type: 'video/mp4',
            src: require('assets/video/20.webm')
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
  methods: {
    muteVideo() {
      this.playerOptions.muted = true
    },
    onPlayerReady(player) {
      console.log('player ready!', player)
      this.player.play()
    },
    changeVideo() {
      const video2 = require('assets/video/2.webm')
      this.player.src(video2)
      this.player.load()
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
