<template>
  <button @click="onClick">MyButton</button>
</template>

<script lang="ts">
  import { Component, Prop, Emit, Vue } from 'vue-property-decorator';

  @Component
  export default class MyButton extends Vue {
    @Prop()
    public greet?: string;

    // クリックイベントを親に渡す
    @Emit()
    public click() {
      //
    }

    public onClick() {
      alert(this.greet);
      this.click();
    }
  }
</script>