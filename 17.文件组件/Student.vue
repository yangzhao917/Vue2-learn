<template>
    <div>
        <p>学生姓名：<span>{{studentName}}</span></p>
        <p>学生电话：<span>{{studentPhone}}</span></p>
    </div>
</template>

<script>
export default {
    name: 'Student',
    data() {
        return {
            studentName: '张三',
            studentPhone: '17832323231'
        }
    }
}
</script>