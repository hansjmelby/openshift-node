<template>
  <div class="home">
    <AboutComponent msg=" Template prosjekt for Vue"/>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import AboutComponent from '@/components/AboutComponent.vue'; // @ is an alias to /src

  export default Vue.extend({
    name: 'home',
    components: {
      AboutComponent,
    },
  });
</script>
