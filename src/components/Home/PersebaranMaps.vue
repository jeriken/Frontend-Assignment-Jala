<template>
  <c-box bg="white" rounded="lg" overflow="hidden">
    <c-box m="4">
      <c-text>Persebaran Harga Udang Size 100</c-text>
    </c-box>
    <c-aspect-ratio-box :ratio="16 / 5" bg="gray.600">
      <c-box
        as="iframe"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d127672.280806814!2d32.52908495891268!3d0.31302911611656636!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x177dbc0f9d74b39b%3A0x4538903dd96b6fec!2sKampala%2C%20Uganda!5e0!3m2!1sen!2sng!4v1586053287932!5m2!1sen!2sng"
        frameborder="0"
        allowfullscreen=""
        aria-hidden="false"
        tabindex="0"
        alt="Kampala, Uganda"
      />
    </c-aspect-ratio-box>
    <c-box m="4">
      <c-flex align="center" justify="center">
        <c-text text-align="center">
          <c-flex align="center">
            <c-box h="5" w="5" bg="yellow.800"/><c-box ml="1" mr="2"> > 1 Bulan </c-box>
            <c-box h="5" w="5" bg="blue.800"/><c-box ml="1" mr="2"> > 1 Minggu </c-box> 
            <c-box h="5" w="5" bg="blue.400"/><c-box ml="1" mr="2"> Baru </c-box>
          </c-flex>
        </c-text>
      </c-flex>
    </c-box>
  </c-box>
</template>

<script>
import { CBox, CAspectRatioBox, CFlex } from "@chakra-ui/vue";
export default {
  name: "PersebaranMaps",
  components: {
    CBox,
    CAspectRatioBox,
    CFlex,
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
