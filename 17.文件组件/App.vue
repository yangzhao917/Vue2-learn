<template>
<div>
    <School></School>
    <Student></Student>
</div>
</template>

<script>
// 引入组件
import Student from './Student.vue'
import School from './School.vue'

export default {
    name: 'App',
    // 注册组件
    components: {
        Student,
        School
    }
}
</script>

<style>

</style>