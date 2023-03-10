<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-box borderBottom="1px" borderRadius="md" borderColor="gray.200">
      <c-box m="4">
        <c-text>Riwayat Harga Di Daerah Jawa Tengah</c-text>
      </c-box>
    </c-box>
    <c-box align="center">
      <c-button-group :spacing="0" m="4">
        <c-button
          variant-color="blue"
          variant="outline"
          size="sm"
          @click="
            riwayat = !riwayat;
            prediksi = !prediksi;
          "
        >
          Riwayat
        </c-button>
        <c-button
          variant-color="blue"
          variant="outline"
          size="sm"
          @click="
            prediksi = !prediksi;
            riwayat = !riwayat;
          "
        >
          Prediksi
        </c-button>
      </c-button-group>
    </c-box>
    <c-collapse :starting-height="20" :is-open="riwayat">
      <c-input-group mx="4">
        <c-input type="date" size="sm" roundedRight="0" placeholder="phone number" />
        <c-input type="date" size="sm" roundedLeft="0" placeholder="phone number" />
      </c-input-group>
      <JSCharting
        v-chakra
        m="8"
        height="250"
        :options="chartOptions"
        class="columnChart"
      ></JSCharting>
      <c-alert status="warning" flexDirection="column" m="4">
        <c-text fontSize="sm">Informasi</c-text>
        <c-text fontSize="sm"
          >Perhitungan trend berdasarkan jumlah data supplier di satu area untuk
          mendapatkan nilai rata-rata di setiap area.</c-text
        >
      </c-alert>
      <c-text mx="4" fontSize="sm" color="blue.500" as="u"
        >Lihat detail trend</c-text
      >
    </c-collapse>
    <c-collapse :starting-height="20" :is-open="prediksi">
      <c-text mx="10" fontSize="sm" mb="2"
        ><b>Prediksi seminggu kedepan</b></c-text
      >
      <c-box mx="10">
        <c-grid
          template-columns="repeat(12, 1fr)"
          py="2"
          bg="gray.200"
          borderTop="2px"
          borderRadius="md"
          borderColor="gray.200"
        >
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm"><b>Size</b></c-text>
          </c-grid-item>
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm">Harga Min</c-text>
          </c-grid-item>
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm">Harga Max</c-text>
          </c-grid-item>
        </c-grid>
        <c-grid
          template-columns="repeat(12, 1fr)"
          py="2"
          borderTop="2px"
          borderRadius="md"
          borderColor="gray.200"
          v-for="i in 3"
          :key="i"
        >
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm"><b>30</b></c-text>
          </c-grid-item>
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm">Rp 71.500</c-text>
          </c-grid-item>
          <c-grid-item col-span="4" mx="4">
            <c-text fontSize="sm">Rp 71.500</c-text>
          </c-grid-item>
        </c-grid>
      </c-box>
      <c-alert status="warning" flexDirection="column" m="4">
        <c-text fontSize="sm">Informasi</c-text>
        <c-text fontSize="sm"
          >Hasil diatas merupakan sebuah prediksi dari berdasarkan data yang
          telah tercatat di Jala. Prediksi harga udang ini
          <b>hanya sebagai referensi</b>, bukan sebuah rujukan yang harus
          diikuti. <b>Jala tidak bertanggung jawab</b> atas kerugian yang
          ditimbulkan karena menggunakan prediksi harga udang</c-text
        >
      </c-alert>
      <c-text mx="4" fontSize="sm" color="blue.500" as="u"
        >Lihat detail trend</c-text
      >
    </c-collapse>
    <c-box mb="6" align="center" >
      <c-text fontSize="sm" mb="2">Tertarik untuk berbagi info harga udang?</c-text>
      <c-button variant-color="blue" size="sm"> TAMBAHKAN HARGA DI DAERAH SAYA </c-button>
    </c-box>
  </c-box>
</template>

<script>
import {
  CBox,
  CText,
  CButtonGroup,
  CButton,
  CCollapse,
  CInputGroup,
  CInput,
  CGrid,
  CGridItem,
  CAlert,
} from "@chakra-ui/vue";
import JSCharting from "jscharting-vue";

export default {
  name: "RiwayatHarga",
  components: {
    CBox,
    CText,
    CButtonGroup,
    CButton,
    CCollapse,
    CInputGroup,
    CInput,
    JSCharting,
    CGrid,
    CGridItem,
    CAlert,
  },
  data() {
    return {
      riwayat: true,
      prediksi: false,
      chartOptions: {
        type: "line",
        series: [
          {
            points: [
              { x: "A", y: 40 },
              { x: "B", y: 30 },
              { x: "C", y: 35 },
              { x: "D", y: 40 },
              { x: "E", y: 30 },
              { x: "F", y: 35 },
              { x: "G", y: 40 },
              { x: "H", y: 30 },
              { x: "J", y: 35 },
              { x: "K", y: 40 },
              { x: "L", y: 30 },
              { x: "M", y: 35 },
            ],
          },
          {
            points: [
              { x: "A", y: 30 },
              { x: "B", y: 50 },
              { x: "C", y: 65 },
              { x: "D", y: 10 },
              { x: "E", y: 60 },
              { x: "F", y: 15 },
              { x: "G", y: 40 },
              { x: "H", y: 60 },
              { x: "J", y: 75 },
              { x: "K", y: 90 },
              { x: "L", y: 10 },
              { x: "M", y: 55 },
            ],
          },
        ],
      },
    };
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
