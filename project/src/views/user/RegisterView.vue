<script setup>
import UserLayout from '@/layouts/UserLayout.vue'
import { useRouter } from 'vue-router'
</script>
<template>
    <UserLayout>
      <div class="signup-container">
        <div class="image-section">
          <img src="https://cdn.readawrite.com/articles/8588/8587149/thumbnail/small.gif?1" alt="Basic First Aid Logo" class="logo" />
        </div>
        <div class="signup-box">
          <h2>สมัครสมาชิก / Sign in</h2>
          <form @submit.prevent="register">
            <div class="input-group">
              <label for="email">Email</label>
              <input type="email" id="email" placeholder="Email" v-model="email" />
            </div>
            <div class="input-group name-fields">
              <div>
                <label for="first-name">ชื่อ</label>
                <input type="text" id="first-name" placeholder="ชื่อจริง" v-model="firstName" />
              </div>
              <div>
                <label for="last-name">นามสกุล</label>
                <input type="text" id="last-name" placeholder="นามสกุล" v-model="lastName" />
              </div>
            </div>
            <div class="input-group">
              <label for="password">รหัสผ่าน</label>
              <input type="password" id="password" placeholder="Password" v-model="password" />
            </div>
            <div class="input-group">
              <label for="confirm-password">รหัสผ่านอีกครั้ง</label>
              <input type="password" id="confirm-password" placeholder="Password" v-model="confirmPassword" />
            </div>
            <button type="submit" class="signup-button">
              <RouterLink :to="{name: 'home'}">สมัครสมาชิก</RouterLink>
            </button>
          </form>
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
.signup-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #ffffff;
}

.signup-box {
  background-color: #fff;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  width: 300px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.signup-box h2 {
  color: #1e73be;
  margin-bottom: 20px;
  text-align: center;
}

.image-section {
  text-align: center;
  margin-right: 50px;
}

.image-section .logo {
  width: 150px;
  margin-bottom: 20px;
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

.name-fields {
  display: flex;
  justify-content: space-between;
}

.name-fields div {
  width: 48%;
}

.signup-button {
  width: 100%;
  padding: 10px;
  background-color: #f48c42;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

.signup-button:hover {
  background-color: #e67e34;
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