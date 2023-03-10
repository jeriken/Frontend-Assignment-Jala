<template>
  <c-box bg="white" rounded="lg" overflow="hidden" m="4">
    <c-box borderBottom="1px" borderRadius="md" borderColor="gray.200">
      <c-box m="4">
        <c-text>Harga Lainnya</c-text>
      </c-box>
    </c-box>
    <c-grid
      template-columns="repeat(10, 1fr)"
      py="2"
      borderTop="2px"
      borderRadius="md"
      borderColor="gray.200"
    >
      <c-grid-item col-span="2" gap="4" v-for="i in 5" :key="i">
        <c-box bg="gray.100" m="4" py="4" px="8" rounded="lg">
          <c-grid template-columns="repeat(12, 1fr)">
            <c-grid-item col-span="6">
              <c-text color="blue.500" fontSize="sm" mb="2"
                ><b>DKI JAKARTA</b></c-text
              >
              <c-text color="blue.500" fontSize="xs">JAKARTA UTARA</c-text>
              <c-text fontSize="xs">Size 100:</c-text>
              <c-text fontSize="sm" my="2">Rp 48.000</c-text>
            </c-grid-item>
            <c-grid-item col-span="6">
              <c-text fontSize="sm">09 Maret 2023</c-text>
              <c-text fontSize="xs">Supplier:</c-text>
              <c-text fontSize="xs"><b>B***************DS</b></c-text>
              <c-text fontSize="sm" my="2">+62xxxxxxxxx</c-text>
            </c-grid-item>
          </c-grid>
          <c-grid template-columns="repeat(12, 1fr)">
            <c-grid-item col-span="6">
              <c-button size="sm" variant-color="blue">LIHAT DETAIL</c-button>
            </c-grid-item>
            <c-grid-item col-span="6">
              <c-button size="sm" variant-color="blue" variant="outline"
                >LIHAT KONTAK</c-button
              >
            </c-grid-item>
          </c-grid>
          <c-flex justify="center" mt="4">
            <c-simple-grid :columns="1" text-align="center">
              <c-text fontSize="sm" mx="4">11</c-text>
              <c-text fontSize="xs">shares</c-text>
            </c-simple-grid>
            <c-icon-button
              isRound="true"
              variant-color="blue"
              size="sm"
              icon="facebook"
              mr="2"
            />
            <c-icon-button
              isRound="true"
              variant-color="green"
              size="sm"
              icon="facebook"
              mr="2"
            />
            <c-icon-button
              isRound="true"
              variant-color="cyan"
              size="sm"
              icon="facebook"
              mr="2"
            />
          </c-flex>
        </c-box>
      </c-grid-item>
    </c-grid>
  </c-box>
</template>

<script>
import {
  CBox,
  CText,
  CGrid,
  CGridItem,
  CButton,
  CIconButton,
  CFlex,
  CSimpleGrid,
} from "@chakra-ui/vue";
export default {
  name: "HargaLain",
  components: {
    CBox,
    CText,
    CGrid,
    CGridItem,
    CButton,
    CIconButton,
    CFlex,
    CSimpleGrid,
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
