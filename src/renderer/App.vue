<template>
    <div id="app">
        <div class="app-title" @mousedown.passive="handleMousedown">
            标题栏
        </div>
        <router-view>
        </router-view>
    </div>
</template>

<script>
export default {
    name: 'my-project',
    methods: {
        handleMousedown (e) {
            if (e.button === 2) {
                e.preventDefault();
            }
        }
    }
}
</script>

<style>
.app {
    overflow: hidden;
}
.app-title {
    height: 20px;
    background-color: #4fc08d;
    position: relative;
    z-index: 100;
    -webkit-app-region: drag;
}
</style>
