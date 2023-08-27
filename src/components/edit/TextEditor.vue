<script setup lang="ts">
import {ref} from "vue";
const eidtorContainer = ref({style: true});

const comment = ref("");

const props = defineProps({
    placeholder: {
        type: String,
        default: ""
    }
});

</script>

<template>
    <div>
    <textarea :class="eidtorContainer" v-model="comment" :placeholder="props.placeholder"></textarea>
    <p/>
    <button type="button" @click.prevent="$emit('submit', comment)">提交</button>
    </div>
</template>

<style scoped>
.eidtorContainer {
    width: auto;
    height: 150px;
}
</style>