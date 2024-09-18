<script setup>
import UserLayout from '@/layouts/UserLayout.vue'
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
                <div class="form-group">
                <label for="name">Name:</label>
                <input v-model="name" type="text" id="name" />
                </div>
                <div class="form-group">
                <label for="address">My Address:</label>
                <input v-model="address" type="text" id="address" />
                </div>
                <div class="form-group">
                <label for="email">Email:</label>
                <input v-model="email" type="email" id="email" />
                </div>
                <div class="form-group">
                <label for="tel">Tel:</label>
                <input v-model="tel" type="tel" id="tel" />
                </div>
            </div>
            <div class="profile-actions">
                <button @click="saveProfile" class="btn-save">SAVE PROFILE</button>
            </div>
            </div>
        </div>
    </UserLayout>
</template>

<style scoped>
.profile-container {
  width: 400px;
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
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 20px;
}

.form-group {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-bottom: 15px;
}

.form-group label {
  width: 30%;
  text-align: left;
  font-weight: bold;
}

.form-group input {
  width: 65%;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.profile-actions {
  text-align: center;
}

.btn-save {
  background-color: #ff5722;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}

.btn-save:hover {
  opacity: 0.8;
}
</style>
