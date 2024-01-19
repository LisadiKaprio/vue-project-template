<template>
  <div>
    <v-card v-bind:title="combinedTitle" variant="outlined" class="ma-3">
      <v-card-actions>
        <v-btn @click="randomizeKaomoji()">
          Click me!
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-facing-decorator'


@Component
export default class CardComponent extends Vue {
  @Prop({ required: true, default: 'Hello World!' }) title: string

  private kaomojis = [
    '^_^',
    ':3',
    '>.<',
    '^.^',
    'o_o',
  ]
  private kaomojiIndex = Math.floor(Math.random() * this.kaomojis.length)

  public randomizeKaomoji() {
    let index = this.kaomojiIndex
    while (index === this.kaomojiIndex) index = Math.floor(Math.random() * this.kaomojis.length)
    this.kaomojiIndex = index
  }

  public get combinedTitle() {
    return this.title + ' ' + this.kaomojis[this.kaomojiIndex]
  }
}
</script>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
