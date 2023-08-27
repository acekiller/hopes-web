
<script setup lang="ts">
import { ref } from "vue";
const account = ref("");
const password = ref("");

function login() {
    console.log(account.value, password.value);
}

function forgot() {
    console.log("forgot");
}

</script>

<template>
    <div class="login" id="loginContainer" width="300px">
        <form>
            <div class="flexContainer inputContainer"><label class="accountLabel"/><input class="flexAuto" type="text" v-model="account" placeholder="用户名或手机号" /></div>
        <p />
        <input type="password" v-model="password" placeholder="请输入8～20位密码" />
        <p />
        <div class="flexContainer"><input type="submit" @click.prevent.stop="login" value="登录"><input type="button" class="forgetPwd" @click.prevent.stop="forgot" value="找回密码" /></div>
    </form>
    </div>
</template>

<style scoped>
    .accountLabel {
        background-image: url("../../assets/login_icons.png");
        background-position-y: -48px;
        width: 38px;
        height: 100%;
    }

    .inputContainer {
        height: 38px;
        border-color: lightgray;
        border-width: 1px;
        border-style: solid;
        border-radius: 4px;
    }

    input {
        margin: 4px 4px;
        border-style: none;
    }

    .login {
        width: 100%;
    }

    .flexContainer {
        width: 100%;
        display: flex;
    }

    .flexAuto {
        flex: 1;
        width: auto;
    }

    .forgetPwd {
        padding: 0 10px;
        margin-left: 10px;
        width: fit-content;
    }

</style>