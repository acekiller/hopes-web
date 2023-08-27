
<script setup lang="ts">
console.log("App");
import {onMounted, onBeforeMount, defineAsyncComponent } from "vue";

import MainHeader from "./pages/home/MainHeader.vue";


import PageBase from "./pages/PageBase.vue";
import LoginRegister from "./components/account/LoginRegister.vue";

console.log("App 1");
onMounted(async () => {
  console.log("onMounted");
})

onBeforeMount(async () => {
  console.log("onBeforeMount");
})


</script>

<template>

  <PageBase ref="PageRef">
  <template v-slot:header>
    <MainHeader title="星星之光(HOPES)" />
  </template>
  <template v-slot:leftBody>
    <b>Welcome</b>
  </template>
  <template v-slot:content>Content</template>
  <template #rightBody>
    <LoginRegister :isRegister="false" />
  </template>
  <template v-slot:footer>
    <div>
      <center>
        Footer
        <p/>
        2023@ccc
      </center>
    </div>
  </template>
  </PageBase>

</template>