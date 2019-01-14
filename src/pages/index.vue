<template>
    <div class="container">
        <duty />
        <warning />
        <cloud />
        <security />
    </div>
</template>

<script>
    import './index.scss'
    import duty from '@/components/duty/duty'
    import warning from '@/components/warning/warning'
    import cloud from '@/components/cloud/cloud'
    import security from '@/components/security/security'
    export default {
        name: "index",
        data(){
            return{

            }
        },
        methods(){

        },
        components:{
            duty,warning,cloud,security
        }
    }
</script>

<style lang="scss" scoped>

</style>