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
      statusMatch: "default",
    }
  },
  components: {
    AppContainer,
    InteractScreen
  },
  methods: {
    onHandleBeforeStart(config) {
      console.log('running before start', config)

      this.statusMatch = 'match';
    }
  },
}
</script>

<style lang="scss">

</style>
