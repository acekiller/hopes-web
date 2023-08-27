<script setup lang="ts">
    const props = defineProps({title: {type: String, default: "HOPES"}});
</script>

<template>
    <div id="mainheader"><h1>{{ props.title }}</h1></div>
</template>

<!--
<script>
export default {
    name: "MainHeader",
    props: {
        title: String
    }
}
</script>
-->

<style scoped>
    #mainheader{
        width: 100%;
        height: 60px;
        align-content: center;
    }
    h1 {
        text-align: center;
    }
</style>