<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-grid
      template-columns="repeat(12, 1fr)"
      borderBottom="1px"
      borderRadius="md"
      borderColor="gray.200"
    >
      <c-grid-item col-span="4">
        <c-box m="4">
          <c-text>List Harga Udang</c-text>
        </c-box>
      </c-grid-item>
      <c-grid-item col-start="12" col-end="12">
        <c-box m="4">
          <c-button variant-color="blue" size="xs">TAMBAHKAN HARGA</c-button>
        </c-box>
      </c-grid-item>
    </c-grid>
    <c-box maxH="500" minH="400" overflow="scroll">
      <c-grid
        template-columns="repeat(12, 1fr)"
        bg="gray.100"
        py="2"
        borderY="1px"
        borderRadius="md"
        borderColor="gray.200"
      >
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="sm">Tanggal</c-text>
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="sm">Lokasi</c-text>
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="sm">Supplier</c-text>
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="sm">Harga {{ size }}</c-text>
        </c-grid-item>
        <c-grid-item col-span="4"> </c-grid-item>
      </c-grid>
      <c-grid
        template-columns="repeat(12, 1fr)"
        py="2"
        border="1px"
        borderRadius="md"
        borderColor="gray.200"
        v-for="(item, index) in data"
        :key="index"
      >
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="xs">{{ date(item.created_at) }}</c-text>
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="xs" color="blue.500">{{
            item.region.province_name
          }}</c-text>
          <c-text fontSize="xs">{{ item.region.regency_name }}</c-text>
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="xs"
            ><b>{{ item.creator.name }}</b></c-text
          >
        </c-grid-item>
        <c-grid-item col-span="2" mx="4">
          <c-text fontSize="xs">{{ cv(item[size]) }}</c-text>
        </c-grid-item>
        <c-grid-item col-span="4">
          <c-flex justify="right" mr="4">
            <a :href="'/udang/' + index">
            <c-button
              variant-color="blue"
              size="sm"
              mx="2"
              >LIHAT DETAIL</c-button
            >
            </a>
            <c-text fontSize="sm" mx="2">11</c-text>
            <c-text fontSize="xs">shares</c-text>
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
        </c-grid-item>
      </c-grid>
    </c-box>
  </c-box>
</template>

<script>
import {
  CText,
  CBox,
  CButton,
  CGrid,
  CGridItem,
  CFlex,
  CIconButton,
} from "@chakra-ui/vue";

export default {
  name: "ListUdang",
  components: {
    CText,
    CBox,
    CButton,
    CGrid,
    CGridItem,
    CFlex,
    CIconButton,
  },
  props: {
    data: String,
    size: String,
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
