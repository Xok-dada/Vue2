<template>
    <div>
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