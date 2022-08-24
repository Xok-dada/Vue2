<template>
    <div>
        <h1 class="title">你好</h1>
        <SchoolName/>
        <hr>
        <StudentName/>
    </div>
</template>

<script>
    //引入组件
    import StudentName from './components/StudentName'
    import SchoolName from './components/SchoolName'
    
    export default {
        name:'App',
        components:{StudentName,SchoolName},
    }
</script>

<style scoped>
	.title{
		color: red;
	}
</style>