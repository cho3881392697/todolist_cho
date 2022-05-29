<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const props = defineProps({
  countryName: {
    type: String,
    required: true,
  },
});
const cityname = ref();
onMounted(async () => {
  const res = await axios.get("/api/countries/" + props.countryName);
  cityname.value = res.data;
});
</script>

<template>
  <div>
    <h1>City</h1>
    <div v-if="cityname">
      <div v-for="city in cityname">
        <router-link :to="'/city/' + city.name.String">{{
          city.name.String
        }}</router-link>
      </div>
    </div>
    <div v-else>町が見つかりませんでした</div>
  </div>
</template>
