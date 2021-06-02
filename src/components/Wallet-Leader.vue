<template>
  <div class="wallet-leader">
    <div id="fun-wallet-leader" style="display:none;">
      <div class="fun-wallet-container">
        <iframe
          allow="camera"
          id="funwallet-iframe"
          is-fun-wallet="true"
          is-leader="true"
          @load="leaderLoaded"
          frameborder="0"
        ></iframe>
      </div>
    </div>
    <div id="fun-wallet-darken"></div>
  </div>
</template>

<script>
export default {
  name: 'WalletLeader',
  props: {
    registerEventListeners: {
      type: Function,
    },
  },
  methods: {
    leaderLoaded() {
      window.funwallet.sdk.init();
      this.registerEventListeners();
    },
  },
};
</script>
