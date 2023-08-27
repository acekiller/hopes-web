<style>
.invalid {
    color: red;
}
</style>

<script setup lang="ts">
import { ref, computed } from "vue";
const phone = ref("");
const username = ref("");
const password = ref("");
const smsCode = ref("");

function register() {
    console.log(phone.value, password.value, smsCode.value);
}

// const usernameIsError = computed(() => {
//     return usernameInvalid.value.isInvalid;
// });

// const usernameErrorMsg = computed(() => {
//     return usernameInvalid.value.isInvalid ? "用户名不能超过10个字符" : "";
// });

const usernameInput = computed(() => {
    return {
        invalid: usernameStatus.value.invalid,
    }
});

const usernameStatus = computed(() => {
    console.log(username.value);
    return {
        invalid: username.value.length > 10,
        errMsg: username.value.length > 10 ? "用户名不能超过10个字符" : "",
    }
});

function sendSmsCode() {
    console.log("发送验证码");
}

</script>

<template>
    <div class="register_div">
        <form>
            <div>
                <input id="phone" type="text" v-model="phone" placeholder="请输入手机号" /><p />
                <input id="username" :class="usernameInput" type="text" v-model="username" placeholder="请输入用户名" /><p />
                <text v-show="usernameStatus.invalid">{{ usernameStatus.errMsg }}</text> <p />
                <input id="password" type="password" v-model="password" placeholder="请输入8～20位密码" /><p />
            </div>
            <div class="smsCodeContainer">
                <input id="smsCode" class="smsCode" type="text" v-model="smsCode" placeholder="请输入验证码" />
                <input type="button" id="sendCode" value="发送" @click="sendSmsCode" /><p />
            </div>
            <input id="submit" type="submit" @click.prevent.stop="register" value="注册">
        </form>
    </div>
</template>

<style scoped>
    input {
        height: 30px;
        margin-top: 10px;

        padding-left: 4px;
        padding-right: 4px;

        border-color: lightgray;
        border-width: 1px;
        border-style: solid;
        border-radius: 4px;
        
        width: calc(100% - 10px);
    }

    .smsCodeContainer {
        display: flex;
        width: 100%;
    }

    input[id="smsCode"] {
        width: auto;
        flex: 1;
    }

    input[id="sendCode"] {
        padding: 0px 10px;
        margin-left: 10px;
        width: fit-content;
    }

    input[id="submit"] {
        width: 100%;
    }
    
    .register_div {
        width: 100%;
    }
</style>