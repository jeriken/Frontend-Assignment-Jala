<template>
  <div class="about">
    <detail-bar />
    <c-grid template-columns="repeat(12, 1fr)" m="4" gap="4">
      <c-grid-item col-span="7">
        <detail-harga :data="data[id]" />
      </c-grid-item>
      <c-grid-item col-span="5">
        <riwayat-harga/>
      </c-grid-item>
    </c-grid>
    <harga-lain/>
    <bottom-bar />
  </div>
</template>
<script>
// @ is an alias to /src
import DetailBar from "@/components/Detail/DetailBar.vue";
import BottomBar from "@/components/Home/BottomBar.vue";
import DetailHarga from "@/components/Detail/DetailHarga.vue";
import RiwayatHarga from "@/components/Detail/RiwayatHarga.vue";
import HargaLain from "@/components/Detail/HargaLain.vue";
import { CGrid, CGridItem } from "@chakra-ui/vue";
import ShrimpPrices from "@/assets/shrimp_prices.json";

export default {
  name: "DetailView",
  components: {
    DetailBar,
    BottomBar,
    DetailHarga,
    RiwayatHarga,
    HargaLain,
    CGrid,
    CGridItem,
  },
  data() {
    return {
      id : this.$route.params.id,
      data: ShrimpPrices,
    };
  },
  methods: {
  }
};
</script>