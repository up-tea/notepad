<template>
  <div class="named-slot-child">
    <h2>{{message}}</h2>
    <slot name="first">
      <p>first slot</p>
    </slot>
    <slot name="second">
      <p>second slot</p>
    </slot>
    <slot name="third">
      <p>third slot</p>
    </slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "名前付きスロット"
    };
  }
};
</script>