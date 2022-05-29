<script setup>
import axios from "axios";
const sendGet = () => axios.get("https://eo7orm4jagjwi2b.m.pipedream.net");
const sendPost = () =>
  axios.post("https://eo7orm4jagjwi2b.m.pipedream.net", {
    traQID: "cho",
    grade: 22,
  });
const sendPut = () =>
  axios.put("https://eo7orm4jagjwi2b.m.pipedream.net", {
    testData: { string: "string", number: 1 },
  });
const sendDelete = () =>
  axios.delete("https://eo7orm4jagjwi2b.m.pipedream.net", {
    data: { po: 1 },
  });
</script>

<template>
  <div>
    <button @click="sendGet">GET</button>
    <button @click="sendPost">POST</button>
    <button @click="sendPut">PUT</button>
    <button @click="sendDelete">DELETE</button>
  </div>
</template>
