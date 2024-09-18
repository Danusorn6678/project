<script setup>
import UserLayout from '@/layouts/UserLayout.vue'
import { useRouter } from 'vue-router'



</script>
<template>
    <UserLayout>
        <div class="login-container">
            <div class="image-section">
                <img src="https://cdn.readawrite.com/articles/8588/8587149/thumbnail/small.gif?1" alt="Basic First Aid Logo" class="logo" />
            </div>
            <div class="login-box">
                <div class="form-section">
                    <h2>เข้าสู่ระบบ / Login</h2>
                    <form @submit.prevent="login">
                        <div class="input-group">
                            <label for="username">ชื่อบัญชี</label>
                            <input type="text" id="username" placeholder="Username/Email" v-model="username" />
                        </div>
                        <div class="input-group">
                            <label for="password">รหัสผ่าน</label>
                            <input type="password" id="password" placeholder="Password" v-model="password" />
                        </div>
                        <div class="remember-me">
                            <input type="checkbox" id="remember-me" v-model="rememberMe" />
                            <label for="remember-me">Remember Me</label>
                        </div>
                        <button type="submit" class="login-button">
                            <RouterLink :to="{name: 'home'}">เข้าสู่ระบบ</RouterLink>
                        </button>
                    </form>
                    <div class="signup-link">
                        <p>ยังไม่มีบัญชี ? <a href="#">
                            <RouterLink :to="{name: 'register'}">สมัครสมาชิก</RouterLink>
                        </a></p>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer-features">
            <div class="feature-item">
                <img src="" alt="Free Shipping" />
                <p>ส่งฟรี ทั่วไทย<br />เมื่อช้อป 399.-*</p>
            </div>
            <div class="feature-item">
                <img src="" alt="Warranty" />
                <p>รับประกันความพึงพอใจ<br />เปลี่ยน/คืนสินค้าใน 30 วัน*</p>
            </div>
            <div class="feature-item">
                <img src="" alt="Fast Delivery" />
                <p>จัดส่งสินค้าภายใน<br />วันถัดไปทันที</p>
            </div>
        </div>
    </UserLayout>
</template>
<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f48c42;
}

.login-box {
  display: flex;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}

.image-section {
  text-align: center;
  margin-right: 50px;
}

.image-section .logo {
  width: 150px;
  margin-bottom: 20px;
}

.form-section {
  padding: 20px;
  width: 300px;
}

.form-section h2 {
  margin-bottom: 20px;
  color: #1e73be;
}

.input-group {
  margin-bottom: 15px;
}

.input-group label {
  display: block;
  margin-bottom: 5px;
}

.input-group input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.remember-me {
  margin-bottom: 15px;
  display: flex;
  align-items: center;
}

.remember-me input {
  margin-right: 5px;
}

.login-button {
  width: 100%;
  padding: 10px;
  background-color: #f48c42;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

.login-button:hover {
  background-color: #e67e34;
}

.signup-link {
  margin-top: 20px;
  text-align: center;
}

.signup-link a {
  color: #ff4a2d;
  text-decoration: none;
}

.signup-link a:hover {
  text-decoration: underline;
}

.footer-features {
  display: flex;
  justify-content: space-around;
  width: 100%;
  padding: 20px;
  background-color: #fd650cde;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

</style>