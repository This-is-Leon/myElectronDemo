<template>
    <div class="login-page">
        <div class="login-container">
            <h2>Login</h2>
            <form @submit.prevent="login">
                <div class="form-group">
                    <label for="username">Username:</label>
                    <input type="text" id="username" v-model="username" required>
                </div>
                <div class="form-group">
                    <label for="password">Password:</label>
                    <input type="password" id="password" v-model="password" required>
                </div>
                <button type="submit" class="btn">Login</button>
            </form>
            <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            username: 'admin',
            password: '123',
            errorMessage: ''
        }
    },
    methods: {
        login () {
            // 这里只是模拟登录过程，实际上你需要发送一个请求到服务器进行验证  
            if (this.username === 'admin' && this.password === '123') {
                // 登录成功，跳转到其他页面或执行其他操作  
                alert('Login successful!');
                this.$router.push('/home');
                // 清除错误信息（如果有的话）  
                this.errorMessage = '';
            } else {
                // 登录失败，显示错误信息  
                this.errorMessage = 'Incorrect username or password';
            }
        }
    },
}
</script>

<style scoped>
.login-page {
    font-family: Arial, sans-serif;
    /* background-color: #f0f0f0; */
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.login-container {
    width: 320px;
    padding: 20px;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.login-container h2 {
    text-align: center;
    margin-bottom: 20px;
}

.form-group {
    margin-bottom: 15px;
}

.form-group label {
    display: block;
    margin-bottom: 5px;
}

.form-group input {
    width: 100%;
    padding: 10px;
    border-radius: 3px;
    border: 1px solid #ccc;
}

.btn {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #42c98c;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

.btn:hover {
    background-color: #23a153;
}

.error-message {
    color: red;
    text-align: center;
    margin-top: 10px;
}
</style>