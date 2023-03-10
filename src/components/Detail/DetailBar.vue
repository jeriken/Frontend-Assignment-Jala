<template>
  <c-box p="4" mb="4" bg="white">
    <c-grid template-columns="repeat(12, 1fr)" gap="6">
      <c-grid-item col-span="6" mx="4">
        <c-text color="blue.500"><b>JAWA TENGAH</b></c-text>
        <c-text fontSize="sm" color="gray.500">KEBUMEN</c-text>
      </c-grid-item>
      <c-grid-item col-span="6" text-align="right" mx="4" my="2">
        <c-button variant-color="green" size="xs">Kembali</c-button>
      </c-grid-item>
    </c-grid>
  </c-box>
</template>

<script>
import { CBox, CGrid, CGridItem, CButton, CText } from "@chakra-ui/vue";
export default {
  name: "DetailBar",
  components: {
    CBox,
    CGrid,
    CGridItem,
    CButton,
    CText,
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
