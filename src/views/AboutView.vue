<template>
  <CardComponent title="About page!" />
  <v-btn to="/">
    Back to Hello World
  </v-btn>
</template>
<script lang="ts">
import CardComponent from '../components/CardComponent.vue'
import { Component, Vue } from 'vue-facing-decorator'

@Component({
  components: {
    CardComponent,
  },
})
export default class AboutView extends Vue {
  // ...
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
