<template>
  <div class="slot">
    <h1>スロット、名前付きスロット、スコープ付きスロット</h1>
    <p>{{message}}</p>
    <SlotChild />
    <NamedSlotChild />
    <ScopedSlotChild />
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
      message: "This is Slot Parent Component"
    };
  }
};
</script>
