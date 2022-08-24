<template>
    <div class="app">
        <h1>{{msg}},学生姓名是：{{stuName}}</h1>
        <!-- 通过父组件给子组件传递函数类型的props实现：子给父传递数据 -->
        <SchoolName :getSchoolName='getSchoolName'/>
        <hr>
        <!-- 通过父组件给子组件绑定一个自定义事件实现：子给父传递数据（第一种写法，使用@或v-on） -->
        <!-- <StudentName @atguigu='getStudentName' @demo='m1'/> -->

        <!-- 通过父组件给子组件绑定一个自定义事件实现：子给父传递数据（第二种写法，使用ref） -->
        <StudentName ref="StudentName"/>
        <!-- <StudentName ref="StudentName" @click.native="show"/> -->
    </div>
</template>

<script>
    //引入组件
    import StudentName from './components/StudentName'
    import SchoolName from './components/SchoolName'
    
    export default {
        name:'App',
        components:{StudentName,SchoolName},
        data(){
            return {
                msg:'你好啊！',
                stuName:''
            }
        },
        methods: {
            getSchoolName(name){
                console.log('App收到了学校名:',name);
            },
            getStudentName(name,...params){
                console.log('App收到了学生名:',name,params);
                this.stuName = name
            },
            m1(){
                console.log('demo事件被触发了');
            },
            show(){
                alert(123)
            }
        },
        mounted() {
            this.$refs.StudentName.$on('atguigu',this.getStudentName) //绑定自定义事件
            // this.$refs.StudentName.$once('atguigu',this.getStudentName) //绑定自定义事件（一次性）
        },
    }
</script>

<style scoped>
    .app{
        background-color: gray;
        padding: 5px;
    }
</style>