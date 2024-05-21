<template>
    <div id="wrapper">
        <main class="main-part">
            <div class="left-side">
                <span class="title">
                    Desktop Games
                </span>
            </div>
            <div class="right-side">

                <login-page></login-page>
                <!-- <system-information></system-information> -->
            </div>
        </main>
    </div>
</template>

<script>
import SystemInformation from './LandingPage/SystemInformation'
import LoginPage from '../pages/admin/login.vue'
export default {
    name: 'landing-page',
    components: { SystemInformation, LoginPage },
    methods: {
        open (link) {
            this.$electron.shell.openExternal(link)
        }
    }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro");

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: "Source Sans Pro", sans-serif;
}

#wrapper {
    background-image: url("../assets/cover_1.jpg");
    background-size: 100% 100%;
    height: calc(100vh - 20px);
    width: 100vw;
    overflow: hidden;
}

#logo {
    height: auto;
    margin-bottom: 20px;
    width: 420px;
}

main {
    display: flex;
    justify-content: space-between;
}

main > div {
    flex-basis: 50%;
}

.left-side {
    display: flex;
    flex-direction: column;
    width: 520px;
    height: 740px;
}

.welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
}

.title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
}

.title.alt {
    font-size: 18px;
    margin-bottom: 10px;
}

.doc p {
    color: black;
    margin-bottom: 10px;
}

.doc button {
    font-size: 0.8em;
    cursor: pointer;
    outline: none;
    padding: 0.75em 2em;
    border-radius: 2em;
    display: inline-block;
    color: #fff;
    background-color: #4fc08d;
    transition: all 0.15s ease;
    box-sizing: border-box;
    border: 1px solid #4fc08d;
}

.doc button.alt {
    color: #42b983;
    background-color: transparent;
}
</style>
