<template>
  <div class="home">
    <c-box p="4" mb="4" bg="white" align="center" justify="center">
      <c-grid template-columns="repeat(12, 1fr)" gap="6">
        <c-grid-item col-span="1">Filter: </c-grid-item>
        <c-grid-item col-span="7">
          <c-select v-model="selectedRegion" placeholder="Pilih lokasi" size="sm">
            <option v-for="item in region" :key="item" :value="item.id">
              {{ item.name }}
            </option>
          </c-select>
        </c-grid-item>
        <c-grid-item col-span="2">
          <c-select v-model="selectedSize" size="sm">
            <option v-for="item in size" :key="item" :value="item.value">{{ item.name }}</option>
          </c-select>
        </c-grid-item>
        <c-grid-item col-span="2">
          <c-select v-model="burgerType" placeholder="Vannamei" size="sm">
            <option value="Vannamei">Vannamei</option>
          </c-select>
        </c-grid-item>
      </c-grid>
    </c-box>
    <c-grid template-columns="repeat(12, 1fr)" m="5" gap="4">
      <c-grid-item col-span="7">
        <persebaran-maps />
      </c-grid-item>
      <c-grid-item col-span="5">
        <b>Trend harga di berbagai daerah</b>
        <c-grid mt="4" template-columns="repeat(12, 1fr)" gap="4">
          <c-grid-item col-span="6" v-for="i in 4" :key="i"
            ><trend-harga
          /></c-grid-item>
        </c-grid>
      </c-grid-item>
    </c-grid>
    <c-box m="5">
      <list-udang :data="data" :size="selectedSize" />
    </c-box>
    <bottom-bar />
  </div>
</template>

<script>
// @ is an alias to /src
import BottomBar from "@/components/Home/BottomBar.vue";
import PersebaranMaps from "@/components/Home/PersebaranMaps.vue";
import TrendHarga from "@/components/Home/TrendHarga.vue";
import ListUdang from "@/components/Home/ListUdang.vue";
import { CBox, CGrid, CGridItem, CSelect } from "@chakra-ui/vue";
import RegionData from "@/assets/regions.json";
import ShrimpPrices from "@/assets/shrimp_prices.json";
import ShrimpSizes from "@/assets/sizes.json";

export default {
  name: "HomeView",
  components: {
    CBox,
    CGrid,
    CGridItem,
    CSelect,
    BottomBar,
    PersebaranMaps,
    TrendHarga,
    ListUdang,
  },
  data() {
    return {
      selectedRegion: '',
      selectedSize: 'size_100',
      size: ShrimpSizes,
      region: RegionData,
      data: ShrimpPrices,
    };
  },
};
</script>
