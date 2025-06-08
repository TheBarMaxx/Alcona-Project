<script setup>
import {ElInput} from 'element-plus';
import {ElCheckbox} from 'element-plus';
import {ElButton} from 'element-plus';
import {reactive} from 'vue';
const task = reactive({
    status: false,
    title: ""
});

</script>
<template>
<el-input placeholder="Name" v-model='task.title'></el-input>
<el-checkbox label="Выполнен" v-model='task.title'></el-checkbox>
<el-button type="success">Success</el-button>
</template>