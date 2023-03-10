<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-grid template-columns="repeat(12, 1fr)">
      <c-grid-item col-span="4">
        <c-box m="4">
          <c-text fontSize="sm"><b>Copyright</b>  PT JALA Akuakultur Lestari Alamku © 2023. Privacy Policy.</c-text>
        </c-box>
      </c-grid-item>
      <c-grid-item col-start="12" col-end="12">
        <c-box m="4">
          <c-text fontSize="sm">JALA v1.25.0</c-text>
        </c-box>
      </c-grid-item>
    </c-grid>
  </c-box>
</template>

<script>
import { CBox, CGrid, CGridItem, CText } from "@chakra-ui/vue";

export default {
  name: "BottomBar",
  components: {
    CBox,
    CGrid,
    CGridItem,
    CText
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
