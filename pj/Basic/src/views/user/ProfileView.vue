<script setup>
import UserLayout from '@/layouts/UserLayout.vue'
import { useRouter } from 'vue-router'

</script>

<template>
    <UserLayout>
        <div class="profile-container">
            <h1 class="text-3xl font-bold my-5">MY PROFILE</h1>
            <div class="profile-card">
            <div class="profile-image">
                <img :src="profileImage" alt="Profile Image" />
            </div>
            <div class="profile-details">
                <p><strong>Name:</strong> {{ name }}</p>
                <p><strong>Email:</strong> {{ email }}</p>
                <p><strong>My Address:</strong> {{ address }}</p>
                <p><strong>Tel:</strong> {{ tel }}</p>
            </div>
            <div class="profile-actions">
                <button @click="editProfile" class="btn-edit">
                    <RouterLink :to="{name: 'profilesetting'}">Edit Profile</RouterLink>
                </button>
                <button @click="signOut" class="btn-signout">Sign Out</button>
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

.profile-container {
  width: 300px;
  margin: 0 auto;
  margin-block: 5%;
  padding-top: 50px;
  text-align: center;
}

.profile-card {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.profile-image img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-bottom: 20px;
}

.profile-details {
  text-align: left;
}

.profile-details p {
  margin: 10px 0;
}

.profile-actions {
  margin-top: 20px;
}

.btn-edit {
  background-color: #555;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
  margin-bottom: 10px;
}

.btn-signout {
  background-color: #ff5722;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}

.btn-edit:hover,
.btn-signout:hover {
  opacity: 0.8;
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