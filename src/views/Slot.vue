<template>
  <div class="slot">
    <h1>{{message}}</h1>
    <p>slotは、特定領域の描画内容を、親comopnentにまるまるお願いしたい時に使う</p>
    <p>通常のスロット、名前付きスロット、スコープ付きスロットの3つに分類できる</p>
    <p>通常、スロットのスコープは親に依存し、スコープ内のthisは親componentのobjectを参照する</p>

    <!--通常スロット-->
    <SlotChild>
      <template>
        <p class="to-slot-child-from-parent">親componentから子component(SlotChild)のslotに書き込んでいるよ!</p>
        <p>子compoentの{{slotTag}}部分に埋め込まれるよ!</p>
        <p>上の行でやってるみたいに、scopeは親だから親のリアクティブデータが使えるよ!</p>
      </template>
    </SlotChild>

    <!--名前付きスロット-->
    <NamedSlotChild>
      <template #second>
        <p
          class="to-named-slot-child-from-parent"
        >親componentから子component(NamedSlotChild)のsecond slotに省略記法(#slotname)で書き込んでいるよ!</p>
      </template>
      <template v-slot:third>
        <p
          class="to-named-slot-child-from-parent"
        >親componentから子component(NamedSlotChild)のthird slotに通常記法(v-slot:slotname)で書き込んでいるよ!</p>
      </template>
    </NamedSlotChild>
    <!--スコープ付きスロット-->
    <ScopedSlotChild>
      <template v-slot:first="ai">
        <!--
      ポイント
      子から親にobjectを渡している
      子ではactressという名前で渡したいobjectをbindしてる
      親ではaiという変数名でactressを受け取っている
        -->
        <h5>ケース1</h5>
        <p>{{ai}}</p>
      </template>

      <template #second="{actress}">
        <!--
      ポイント
      子から親にobjectを渡している
      子ではactressという名前で渡したいobjectをbindしてる
      値を受け取る際に、bindした時の名前でobjectの分割代入を行なっている
        -->
        <h5>ケース2</h5>
        <p>{{actress}}</p>
      </template>

      <template #third="data">
        <!--ポイント
      子から親に文字列を渡している
      子ではnamaeという名前で渡したい文字列をbindしてる
      親で値を受け取る時に分割代入を使用していない
      親で値を受け取る時にdataという変数名を使っている
        -->
        <h5>ケース3</h5>
        <p>{{data}}</p>
      </template>

      <template #fourth="{namae}">
        <!--ポイント
      子から親に文字列を渡している
      子ではnamaeという名前で渡したい文字列をbindしてる
      親で値を受け取る時に分割代入を使用している
      子でbindしたデータを親から参照出来つつ、親のリアクティブデータも参照可能(parentData)
        -->
        <h5>ケース4</h5>
        <p>{{namae}}</p>
        <p>{{parentData}}</p>
      </template>
    </ScopedSlotChild>
  </div>
</template>
<script>
import SlotChild from "@/components/SlotChild";
import NamedSlotChild from "@/components/NamedSlotChild";
import ScopedSlotChild from "@/components/ScopedSlotChild";
export default {
  components: {
    SlotChild,
    NamedSlotChild,
    ScopedSlotChild
  },
  data() {
    return {
      message: "スロットについて(Slot.vue)",
      slotTag: "<slot></slot>",
      parentData: "this string is reactive data by parent component"
    };
  }
};
</script>
