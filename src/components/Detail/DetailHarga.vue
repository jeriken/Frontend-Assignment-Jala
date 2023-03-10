<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-box borderBottom="1px" borderRadius="md" borderColor="gray.200">
      <c-box m="4">
        <c-text>Detail Harga Udang</c-text>
      </c-box>
    </c-box>
    <c-grid template-columns="repeat(12, 1fr)" m="4" gap="4">
      <c-grid-item col-span="6">
        <c-text fontSize="xs">{{ date(data.created_at) }}</c-text>
        <c-text fontSize="sm"><b>Udang Vannamei (Penaeus Vannamei)</b></c-text>
      </c-grid-item>
      <c-grid-item col-span="3">
        <c-text fontSize="xs">Supplier:</c-text>
        <c-text fontSize="sm"
          ><b>{{ data.creator.name }}</b></c-text
        >
      </c-grid-item>
      <c-grid-item col-span="3">
        <c-text fontSize="xs">Kontak</c-text>
        <c-text fontSize="sm">+62xxxxxxxxx</c-text>
        <c-text fontSize="sm" color="blue.500" as="u" href="/"
          >Lihat Kontak</c-text
        >
      </c-grid-item>
    </c-grid>
    <c-box mx="10" v-for="item in size" :key="item">
      <c-grid
        template-columns="repeat(12, 1fr)"
        py="2"
        borderTop="2px"
        borderRadius="md"
        borderColor="gray.200"
        v-if="data[item.value] != 0"
      >
        <c-grid-item col-span="4" mx="4">
          <c-text fontSize="sm"
            ><b>{{ item.name }}</b></c-text
          >
        </c-grid-item>
        <c-grid-item col-span="4" mx="4">
          <c-text fontSize="sm">{{ cv(data[item.value]) }}</c-text>
        </c-grid-item>
      </c-grid>
    </c-box>

    <c-grid template-columns="repeat(12, 1fr)" py="4">
      <c-grid-item col-span="9" mx="4">
        <c-text>Catatan</c-text>
        <c-text fontSize="sm">Harga berlaku untuk biomass udang 1 ton</c-text>
        <c-text fontSize="sm"
          >Apabila biomass udang lebihdari 10 ton akan berbeda harga</c-text
        >
      </c-grid-item>
      <c-grid-item col-span="3" text-align="right" mx="4" my="2">
        <c-box
          rounded="lg"
          w="80%"
          p="2"
          border="1px"
          borderRadius="md"
          borderColor="gray.200"
        >
          <c-flex justify="right">
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
  CIconButton,
  CFlex,
  CSimpleGrid,
} from "@chakra-ui/vue";
import ShrimpSizes from "@/assets/sizes.json";

export default {
  name: "DetailHarga",
  components: {
    CBox,
    CText,
    CGrid,
    CGridItem,
    CIconButton,
    CFlex,
    CSimpleGrid,
  },
  props: {
    data: String,
  },
  data() {
    return {
      size: ShrimpSizes,
    };
  },
  methods: {
    cv(num) {
      num = new Intl.NumberFormat("id-ID", {
        style: "currency",
        currency: "IDR",
      }).format(num);

      return num;
    },
    date(date) {
      var dateNew = new Date(date);
      return new Intl.DateTimeFormat("id-ID", {
        day: "2-digit",
        month: "long",
        year: "numeric",
      }).format(dateNew);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
