<template>
  <div class="home">
    <p>{{ greetText }}</p>
    <p v-if="isRegurars">毎度あり</p>
    <p>挨拶した回数：{{ count }}回</p>
    <p>
      <MyButton :greet="greetText" @click="onMyButtonClicked"></MyButton>
    </p>
    <p>
      <ResetButton v-model="greetText"></ResetButton>
    </p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import MyButton from '@/components/MyButton.vue';
import ResetButton from '@/components/ResetButton.vue';

@Component({
  components: {
    MyButton,
    ResetButton,
  },
})
export default class Home extends Vue {
  public greetText: string = 'Hello';
  private count: number = 0;

  public get isRegurars(): boolean {
    return this.count >= 5;
  }

  public onMyButtonClicked(count: number) {
    this.count = count;
    this.greetText = 'こんにちは';
  }
}
</script>
