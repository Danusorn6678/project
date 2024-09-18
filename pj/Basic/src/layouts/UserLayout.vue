<script setup>
import { ref, onMounted } from 'vue'
import { RouterLink, useRouter } from 'vue-router'

const router = useRouter()

const isLoggedIn = ref(false)

onMounted(() => {
    if (localStorage.getItem('isLoggedIn')) {
        isLoggedIn.value = true
    }
})

const login = () => {
    isLoggedIn.value = true
    localStorage.setItem('isLoggedIn', true)
}

const logout = () => {
    isLoggedIn.value = false
    localStorage.removeItem('isLoggedIn')
}
</script>

<template>
    <div class="min-h-screen flex flex-col">
        <header class="navbar bg-orange-500">
            <div class="flex-1 flex items-center">
                <div>
                    <img class="w-13 rounded-full w-[45px] h-[45px]" src="https://png.pngtree.com/png-vector/20190711/ourmid/pngtree-medical-suitcase-icon-png-image_1544275.jpg" alt="Logo">
                </div>
                <div class="ml-3">
                    <RouterLink :to="{ name: 'home' }" class="inline-flex items-center gap-x-2 text-xl font-semibold dark:text-black">
                        Basic First Aid
                    </RouterLink>
                    <div class="mx-3">
                        building confidence to save live
                    </div>
                </div>
            </div>
            <div class="flex items-center">
                <div class="dropdown dropdown-end">
                    <div tabindex="0" role="button" class="btn btn-ghost btn-circle">
                        <div class="indicator">
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-5 w-5"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
                            </svg>
                            <span class="badge badge-sm indicator-item">8</span>
                        </div>
                    </div>
                    <div tabindex="0" class="card card-compact dropdown-content bg-base-100 z-[1] mt-3 w-52 shadow">
                        <div class="card-body">
                            <span class="text-lg font-bold">8 Items</span>
                            <span class="text-info">Subtotal: $999</span>
                            <div class="card-actions">
                                <RouterLink :to="{ name: 'cart' }" class="btn btn-primary btn-block">
                                    View cart
                                </RouterLink>
                            </div>
                        </div>
                    </div>
                </div>
                <button @click="login" v-if="!isLoggedIn" class="btn btn-ghost">
                    <RouterLink :to="{ name: 'login' }">Login</RouterLink>
                </button>
                <div v-else class="dropdown dropdown-end">
                    <div tabindex="0" role="button" class="btn btn-ghost btn-circle avatar">
                        <div class="w-10 rounded-full">
                            <img
                                alt="User Avatar"
                                src="https://img.daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg" />
                        </div>
                    </div>
                    <ul tabindex="0" class="menu menu-sm dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-52 p-2 shadow">
                        <li>
                            <RouterLink :to="{ name: 'profile' }">Profile</RouterLink>
                        </li>
                        <li>
                            <a @click="logout">Logout</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div>
                <input type="text" placeholder="Search" name="search" class="rounded-lg pl-1">
            </div>
        </header>

        <nav class="bg-white border-gray-200 dark:bg-white dark:border-white">
            <div class="max-w-screen-xl mx-auto p-1">
                <ul class="flex justify-between">
                    <li>
                        <a href="#" class="block py-2 px-3 text-black md:dark:bg-transparent" aria-current="page">Home</a>
                    </li>
                    <li>
                        <a href="#" class="block py-2 px-3 text-black rounded">Promotion</a>
                    </li>
                    <li>
                        <button id="dropdownNavbarLink" data-dropdown-toggle="dropdownNavbar" class="flex items-center justify-between w-full py-2 px-3 text-black rounded">อุปกรณ์
                            <svg class="w-2.5 h-2.5 ms-2.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4" />
                            </svg>
                        </button>
                    </li>
                    <li>
                        <a href="#" class="block py-2 px-3 text-black rounded">คำถามที่พบบ่อย</a>
                    </li>
                    <li>
                        <a href="#" class="block py-2 px-3 text-black rounded">ติดต่อเรา</a>
                    </li>
                </ul>
            </div>
        </nav>

        <main class="flex-1">
            <slot></slot>
        </main>

        <footer class="footer bg-base-200 text-base-content p-10">
            <div class="flex">
                <div>
                    <img class="w-13 h-auto" src="" alt="Logo">
                </div>
                <div class="my-auto">
                    <a class="inline-flex items-center gap-x-2 text-xl font-semibold dark:text-black" href="#">
                        Basic First Aid
                    </a>
                    <div class="mx-3">
                        building confidence to save live
                    </div>
                </div>
            </div>
            <nav>
                <h6 class="footer-title text-xl">ศูนย์ช่วยเหลือ</h6>
                <a class="link link-hover">ข้อจำกัดความรับผิดชอบ</a>
                <a class="link link-hover">นโยบายความเป็นส่วนตัว</a>
                <a class="link link-hover">ข้อกำหนดและเงื่อนไข</a>
                <a class="link link-hover">คำถามที่พบบ่อย</a>
                <a class="link link-hover">ติดต่อเรา</a>
            </nav>
            <nav>
                <h6 class="footer-title text-xl">บริการหลังการขาย</h6>
                <a class="link link-hover">วิธีการลงทะเบียน</a>
                <a class="link link-hover">วิธีการสั่งสินค้า</a>
                <a class="link link-hover">วิธีการชำระเงิน</a>
                <a class="link link-hover">แจ้งชำระเงิน</a>
                <a class="link link-hover">การจัดส่งสินค้า</a>
            </nav>
        </footer>
    </div>
</template>

<style scoped>
html, body {
    height: 100%;
    margin: 0;
}

footer {
    background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRpGk2KeSgAi4PQbCeeWGFC86339y-hpxKtFQ&s);
    background-size: cover;
    background-position: center;
}
</style>
