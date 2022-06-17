<template>
<!-- 组件的结构 -->
    <div>
        <div>
            <p>学校名称：<span>{{name}}</span></p>
            <p>学校地址：<span>{{address}}</span></p>
        </div>
    </div>
</template>

<script>
// 组件交互代码
export default {
    name: 'School',
    data(){
        return {
            name: '张三',
            address: '中国上海'
        }
    }
}
</script>