<template>
  <iframe
    style="width: inherit"
    id="fun-wallet-follower"
    :src="url"
    :onload="followerLoaded()"
    is-fun-wallet="true"
    is-follower="true"
    frameBorder="0"
  ></iframe>
</template>

<script>
export default {
  name: 'WalletFollower',
  data: () => {
    return { url: undefined };
  },
  created: function() {
    this.$data.url = window.funwallet.getWalletFollowerURL();
  },
  methods: {
    async followerLoaded() {
      await window.funwallet.sdk.registerFollowerInstance();
    },
  },
};
</script>
