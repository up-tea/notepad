<template>
  <div class="slot-child">
    <h2>{{message}}</h2>
    <p>slotが1つだけの場合は、nameを省略できる</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "通常のスロット(SlotChild.vue)"
    };
  }
};
</script>