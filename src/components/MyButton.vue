<template>
  <button @click="onClick">MyButton</button>
</template>

<script lang="ts">
  import { Component, Prop, Emit, Vue } from 'vue-property-decorator';

  @Component
  export default class MyButton extends Vue {
    @Prop()
    public greet?: string;

    private count: number = 0;

    // クリックイベントを親に渡す
    @Emit()
    public click(count: number) {
      //
    }

    public onClick() {
      alert(this.greet);
      this.count++;
      this.click(this.count);
    }
  }
</script>