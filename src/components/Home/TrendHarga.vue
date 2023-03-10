<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-box m="4">
      <c-text mb="1">JAWA TENGAH</c-text>
      <c-flex align="center" mb="1">
        <c-text fontSize="xs"><b>Rp 56.000</b></c-text>
        <c-badge
          rounded="lg"
          px="2"
          mx="2"
          variant="solid"
          variant-color="green"
          >+ Rp 1.000</c-badge
        >
      </c-flex>
      <c-text fontSize="sm">19 Feb - 26 Feb</c-text>
      <JSCharting
        v-chakra
        height="80"
        :options="chartOptions"
        class="columnChart"
      ></JSCharting>
    </c-box>
  </c-box>
</template>

<script>
import { CBox, CText, CFlex, CBadge } from "@chakra-ui/vue";
import JSCharting from "jscharting-vue";

export default {
  name: "TrendHarga",
  components: {
    JSCharting,
    CBox,
    CText,
    CFlex,
    CBadge,
  },
  data() {
    return {
      chartOptions: {
        type: "line",
        legend_visible: false,
        defaultAxis: {
          defaultTick: { enabled: false },
        },
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
