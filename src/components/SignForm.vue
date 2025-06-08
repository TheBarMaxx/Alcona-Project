<script setup>
import {ref} from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();
const login = ref();
const password = ref();
const success = ref(false); 
const errors = ref();
const clickHandler = () => {
    if(login.value==null || password == null){
        errors.value = "Зарегайся тварь"
        return;
    }
    errors.value = underfined;
    success.value = true;
    router.push({name: "task"})

}
</script>
<template>
<form class="sign-form" >
    <template v-if="!success">
        <input type="text" placeholder="Логин" v-model="login"/>
        <input type="password" placeholder="Пароль" v-model="password"/>
        <button type="button" @click="clickHandler">Go</button>
        <div v-if="errors !=null" class="error--text">{{ errors }}</div>
    </template>
    <div v="else">
        {{ login }} авторизуйтесь
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
    width: 70px;
    margin: auto !important;
}
.error--text{
    color: red;
}
</style>