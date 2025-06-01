<script setup>
import { ref } from 'vue';

const login = ref();
const password = ref();
const success = ref(false)
const errors = ref()
const clickhandler = () => {
    if(login.value == null || password.value == null){
        errors.value = "Пароль и логин обязательны"
        return;
    }
    errors.value = undefined;
    success.value = true;
}
</script>
<template>
<form class="sign-form" >
    <template v-if = "!success">
    <input type="text" placeholder="Логин" v-model="login"/>
    <input type="password" placeholder="Пароль"v-model="password"/>
    <button type="button"@click="clickhandler"></button>
    <div v-if = "errors != null" class="error-text"> {{ errors }}</div>

    </template>
    <div v-else>
        {{ login }}, вы успешно авторизировались
    </div>
</form>
</template>
<style>
.sign-form{
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin: auto !important;
}
.sign-form > button{
    height: 25px;
    width: 50px;
}

.error-text {
    color: red;
}
</style>