<template>
  <c-box p="4" mb="4" bg="white" align="center" justify="center">
    <c-grid template-columns="repeat(12, 1fr)" gap="6">
      <c-grid-item col-span="1">Filter: </c-grid-item>
      <c-grid-item col-span="7">
        <c-select v-model="burgerType" placeholder="Pilih lokasi" size="sm" >
          <option v-for="item in region" :key="item" :value="item.id" >{{ item.name }}</option>
        </c-select>
      </c-grid-item>
      <c-grid-item col-span="2">
        <c-select v-model="burgerType" placeholder="Size 100" size="sm">
          <option value="grilled">Grilled Backyard Burger</option>
        </c-select>
      </c-grid-item>
      <c-grid-item col-span="2">
        <c-select v-model="burgerType" placeholder="Vannamei" size="sm">
          <option value="jucy-lucy">Vannamei</option>
        </c-select>
      </c-grid-item>
    </c-grid>
    {{ region[0].id }}
  </c-box>
</template>

<script>
import { CBox, CGrid, CGridItem, CSelect } from "@chakra-ui/vue";
export default {
  name: "TopBar",
  components: {
    CBox,
    CGrid,
    CGridItem,
    CSelect,
  },
  data() {
    return {

    };
  },
  props: {
    region: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
