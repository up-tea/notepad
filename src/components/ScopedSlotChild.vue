<template>
  <div class="named-slot-child">
    <h2>{{message}}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "スコープ付きスロット"
    };
  }
};
</script>