<template>
    <div>
        <div style="width: 100px;">
            <span class="btn" @click="backLandingPage"><span></span>返回登录页</span>
        </div>
        主页
    </div>
</template>

<script>
export default {
    name: 'home-page',
    methods: {
        backLandingPage () {
            this.$router.push('/')
        }
    }
}
</script>

<style>
.btn {
    cursor: pointer;
}
</style>