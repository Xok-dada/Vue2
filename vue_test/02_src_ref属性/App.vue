<template>
    <div>
        <h1 v-text="msg" ref="title"></h1>
        <button ref="btn" @click="showDOM">点我输出上方的DOM元素</button>
        <SchoolName ref="sch"></SchoolName>
    </div>
</template>

<script>
    //引入School组件
    import SchoolName from './components/SchoolName'
    
    export default {
        name:'App',
        components:{SchoolName},
        data() {
            return {
                msg:'欢迎学习Vue!'
            }
        },
        methods: {
            showDOM(){
                console.log(this.$refs.title);  //真实DOM元素
                console.log(this.$refs.btn);  //真实DOM元素
                console.log(this.$refs.sch);  //School组件的实例对象（vc）
            }
        },
    }
</script>

<style>

</style>