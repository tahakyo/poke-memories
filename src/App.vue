<template>
  <div id="app">
    <AppContainer v-if="statusMatch === 'default'" @onStart="onHandleBeforeStart($event)"/>
    <InteractScreen v-if="statusMatch === 'match'" />
  </div>
</template>

<script>
import AppContainer from './components/AppContainer.vue';
import InteractScreen from './components/InteractScreen.vue';

export default {
  name: 'App',
  data() {
    return {
      settings: {
        totalOfBlocks: 0,
        cardContext: [],
      },
      statusMatch: "default",
    }
  },
  components: {
    AppContainer,
    InteractScreen
  },
  methods: {
    onHandleBeforeStart(config) {
      // console.log('running before start', config)
      this.settings.totalOfBlocks = config.totalOfBlocks;
      const firstCards = Array.from(
        { length: this.settings.totalOfBlocks / 2 },
        (_,i) => i+1,
        );
        console.log(firstCards)

      this.statusMatch = 'match';
    }
  },
}
</script>

<style lang="scss">

</style>
