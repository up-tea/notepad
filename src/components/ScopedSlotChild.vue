<template>
  <div class="named-slot-child">
    <h2>{{message}}</h2>
    <h3>:ai="子のリアクティブデータのobject"でobjectを親から参照できるようにするパターン</h3>

    <slot name="first" :actress="ai">
      <p>first slot</p>
    </slot>

    <slot name="second" :actress="ai">
      <p>second slot</p>
    </slot>

    <h3>:namae="子のリアクティブデータの文字列"で文字列を親から参照できるようにするパターン</h3>

    <slot name="third" :namae="namae">
      <p>third slot</p>
    </slot>

    <slot name="fourth" :namae="namae">
      <p>fourth slot</p>
    </slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "スコープ付きスロット",
      ai: {
        name: "上原亜衣",
        age: 27
      },
      namae: "上原亜衣"
    };
  }
};
</script>