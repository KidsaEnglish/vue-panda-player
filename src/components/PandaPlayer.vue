<template>
  <iframe
    id="panda-player"
    :src="iframeSrc"
    ref="pandaPlayer"
    allow="accelerometer;gyroscope;autoplay;encrypted-media;picture-in-picture"
    allowfullscreen
    style="width: 100%; height: 100%;"
  ></iframe>
</template>

<script>
import { loadScript, unloadScript } from "vue-plugin-load-script";


export default {
  name: "PandaPlayer",
  props: {
    queryParams: {
      type: Object,
      default: () => ({})
    },
    fullscreen: Boolean,
    src: String,
    getCurrentTime: Function,
    onTimeUpdate: Function,
    onProgress: Function,
    onReady: Function,
    onPlay: Function,
    onPause: Function,
    onSeeking: Function,
    onSeeked: Function,
    onEnded: Function,
    onEnterFullscreen: Function,
    onExitFullscreen: Function,
    onCaptionsEnabled: Function,
    onCaptionsDisabled: Function,
    onLanguageChange: Function,
    onCanPlay: Function,
    onError: Function,
    onSpeedUpdate: Function,
  },
  data() {
    return {
      player: null,
      progress: 0,
    };
  },
  computed: {
    iframeSrc() {
      const queryParams = this.buildQueryParams();
      return this.src + (queryParams ? `&${queryParams}` : "");
    }
  },
  mounted() {
    this.loadPandaPlayer();
  },
  beforeUnmount() {
    this.destroyPandaPlayer();
  },
  methods: {
    buildQueryParams() {
      const params = [];
      for (const key in this.queryParams) {
        const value = this.queryParams[key];
        if (value !== undefined && value !== null) {
          params.push(`${encodeURIComponent(key)}=${encodeURIComponent(value)}`);
        }
      }
      return params.join("&");
    },
    loadPandaPlayer() {
      loadScript("https://player.pandavideo.com.br/api.js")
        .then(() => {
          // eslint-disable-next-line no-undef
          this.player = new PandaPlayer("panda-player", {
            onReady: () => {
              window.addEventListener(
                "message",
                this.handleMessageEvent,
                false
              );
            },
          });
        })
        .catch((error) => {
          throw error;
        });
    },
    destroyPandaPlayer() {
      if (this.player) {
        this.player.destroy();
        this.player = null;
      }
      window.removeEventListener('message', this.handleMessageEvent, false);
      unloadScript("https://player.pandavideo.com.br/api.js")
        .then(() => {
          
        })
        .catch((error) => {
          throw error;
        });
    },
    getInternalPlayer() {
      return this.player;
    },
    play() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'play' }, '*');
    },

    pause() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'pause' }, '*');
    },

    togglePlay() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'togglePlay' }, '*');
    },

    destroy() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'destroy' }, '*');
    },

    increaseVolume(step) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'increaseVolume', parameter: step }, '*');
    },

    decreaseVolume(step) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'decreaseVolume', parameter: step }, '*');
    },

    toggleCaptions() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'toggleCaptions' }, '*');
    },

    toggleControls(value) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'toggleControls', parameter: value }, '*');
    },

    exitFullscreen() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'fullscreen.exit' }, '*');
    },

    toggleFullscreen() {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'fullscreen.toggle' }, '*');
    },

    forward(seekTime) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'forward', parameter: seekTime }, '*');
    },

    rewind(seekTime) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'rewind', parameter: seekTime }, '*');
    },

    setCurrentTime(time) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'currentTime', parameter: time }, '*');
    },

    setVolume(volume) {
      const iframe = document.getElementById('panda-player').contentWindow;
      iframe.postMessage({ type: 'volume', parameter: volume }, '*');
    },
    handleMessageEvent(event) {
      const { message } = event.data;
      if(this[message]) {
        this[message]();
      }
    },
    panda_timeupdate() {
      if (this.onTimeUpdate) {
        this.onTimeUpdate();
      }
    },

    panda_progress() {
      if (this.onProgress) {
        this.onProgress();
      }
    },

    panda_ready() {
      if (this.onReady) {
        this.onReady();
      }
    },

    panda_play() {
      if (this.onPlay) {
        this.onPlay();
      }
    },

    panda_pause() {
      if (this.onPause) {
        this.onPause();
      }
    },

    panda_seeking() {
      if (this.onSeeking) {
        this.onSeeking();
      }
    },

    panda_seeked() {
      if (this.onSeeked) {
        this.onSeeked();
      }
    },

    panda_ended() {
      if (this.onEnded) {
        this.onEnded();
      }
    },

    panda_enterfullscreen() {
      if (this.onEnterFullscreen) {
        this.onEnterFullscreen();
      }
    },

    panda_exitfullscreen() {
      if (this.onExitFullscreen) {
        this.onExitFullscreen();
      }
    },

    panda_captionsenabled() {
      if (this.onCaptionsEnabled) {
        this.onCaptionsEnabled();
      }
    },

    panda_captionsdisabled() {
      if (this.onCaptionsDisabled) {
        this.onCaptionsDisabled();
      }
    },

    panda_languagechange() {
      if (this.onLanguageChange) {
        this.onLanguageChange();
      }
    },

    panda_canplay() {
      if (this.onCanPlay) {
        this.onCanPlay();
      }
    },

    panda_error() {
      if (this.onError) {
        this.onError();
      }
    },

    panda_speed_update() {
      if (this.onSpeedUpdate) {
        this.onSpeedUpdate();
      }
    }
  },
};
</script>
