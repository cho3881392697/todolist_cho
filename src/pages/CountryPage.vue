<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const countryname = ref();
onMounted(async () => {
  const res = await axios.get("/api/countryindex");
  countryname.value = res.data;
});
</script>

<template>
  <div>
    <h1>Country</h1>
    <div v-if="countryname">
      <div v-for="country in countryname">
        <router-link :to="'/country/' + country.code.String">{{
          country.name.String
        }}</router-link>
      </div>
    </div>
    <div v-else>国が見つかりませんでした</div>
  </div>
</template>
