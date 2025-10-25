<template>
    <div class="header bg-gray-800 text-white shadow-lg">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center py-4">
                <!-- Logo/Brand -->
                <div class="text-xl font-bold">بناء ولياقة</div>
                
                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-8">
                    <ul class="mainLinks flex space-x-8">
                        <li><a href="#Home" class="hover:text-green-400 transition duration-300">الرئيسية</a></li>
                        <li><a href="#AboutUs" class="hover:text-green-400 transition duration-300">تعرف علينا</a></li>
                        <li><a href="#Dashboard" class="hover:text-green-400 transition duration-300">لوحة البيانات</a></li>
                    </ul>
                    <ul class="access flex space-x-8">
                        <li><a href="#SignOut" class="hover:text-green-400 transition duration-300">تسجيل خروج</a></li>
                        <li><a href="#SignIn" class="hover:text-green-400 transition duration-300">تسجيل دخول</a></li>
                        <li><a href="#SignUp" class="hover:text-green-400 transition duration-300">سجل معنا</a></li>
                    </ul>
                </div>

                <!-- Burger Button for Mobile -->
                <button @click="toggleMenu" class="md:hidden focus:outline-none">
                    <div class="w-6 flex flex-col space-y-1">
                        <span :class="['h-0.5 bg-white transition-all duration-300', isOpen ? 'rotate-45 translate-y-1.5' : '']"></span>
                        <span :class="['h-0.5 bg-white transition-all duration-300', isOpen ? 'opacity-0' : '']"></span>
                        <span :class="['h-0.5 bg-white transition-all duration-300', isOpen ? '-rotate-45 -translate-y-1.5' : '']"></span>
                    </div>
                </button>
            </div>

            <!-- Mobile Menu -->
            <div :class="['md:hidden overflow-hidden transition-all duration-300', isOpen ? 'max-h-96 pb-4' : 'max-h-0']">
                <div class="flex flex-col space-y-4">
                    <a href="#Home" class="hover:text-green-400 transition duration-300 py-2 border-b border-gray-700">الرئيسية</a>
                    <a href="#AboutUs" class="hover:text-green-400 transition duration-300 py-2 border-b border-gray-700">تعرف علينا</a>
                    <a href="#Dashboard" class="hover:text-green-400 transition duration-300 py-2 border-b border-gray-700">لوحة البيانات</a>
                    <a href="#SignOut" class="hover:text-green-400 transition duration-300 py-2 border-b border-gray-700">تسجيل خروج</a>
                    <a href="#SignIn" class="hover:text-green-400 transition duration-300 py-2 border-b border-gray-700">تسجيل دخول</a>
                    <a href="#SignUp" class="hover:text-green-400 transition duration-300 py-2">سجل معنا</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavbarPage',
    data() {
        return {
            isOpen: false
        }
    },
    methods: {
        toggleMenu() {
            this.isOpen = !this.isOpen
        }
    }
}
</script>