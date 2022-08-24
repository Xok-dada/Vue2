<template>
    <div>
        <StudentName name="李四" sex="女" :age="18"></StudentName>
    </div>
</template>

<script>
    //引入StudentName组件
    import StudentName from './components/StudentName'
    
    export default {
        name:'App',
        components:{StudentName},
    }
</script>

<style>

</style>