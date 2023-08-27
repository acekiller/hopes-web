<script setup lang="ts">
import { ref, onMounted, onBeforeMount, computed } from "vue";
import LoginForm from './LoginForm.vue';
import RegisterForm from './RegisterForm.vue';

onMounted(() => {
    console.log("--->onMounted");
})

const props = defineProps({
    isRegister: {
        type: Boolean,
        default: false,
    }
})

const isLogin = ref(false);

onBeforeMount(() => {
    console.log("--->onBeforeMount", props.isRegister);
    isLogin.value = !props.isRegister;
})

function clickLogin() {
    if (isLogin.value) {
        return
    }
    isLogin.value = true;
}

function clickRegister() {
    if (!isLogin.value) {
        return
    }
    isLogin.value = false;
}

const currentStateFrom = computed(() => {
    return isLogin.value ? LoginForm : RegisterForm;
})

</script>

<template>
    <div class="accountContainer">
        <div>
        <a @click.prevent="clickLogin">登录</a> 
        <a @click.prevent="clickRegister">注册</a>
        </div>
        
        <component :is="currentStateFrom" />
    </div>
</template>

<style scoped>
    a {
        margin: 10px;
    }

    .accountContainer {
        width: 250px;

        padding: 10px 10px;
        margin: 10px;

        border-width: 1px;
        border-style: solid;
        border-color: lightgray;
        border-radius: 4px;
    }
</style>