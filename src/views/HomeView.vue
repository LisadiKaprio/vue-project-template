<template>
  <CardComponent title="Hello World!" />
  <v-btn to="/about">
    About
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
export default class HomeView extends Vue {
  // ...
}
</script>
