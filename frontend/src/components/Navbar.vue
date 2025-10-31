<template>
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@200..1000&family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&family=Noto+Kufi+Arabic:wght@100..900&display=swap" rel="stylesheet">
    <div class="header">
        <div class="container">
            <div class="nav-container">
                <!-- Logo/Brand -->
                <div class="brand">بناء ولياقة</div>
                
                <!-- Desktop Menu -->
                <div class="desktop-menu">
                    <ul class="access">
                        <li><a href="#SignOut">تسجيل خروج</a></li>
                        <li><a href="#SignIn">تسجيل دخول</a></li>
                        <li><a href="#SignUp">سجل معنا</a></li>
                    </ul>
                    <ul class="mainLinks">
                        <li><a href="#Home">الرئيسية</a></li>
                        <li><a href="#AboutUs">تعرف علينا</a></li>
                        <li><a href="#Dashboard">لوحة البيانات</a></li>
                    </ul>
                </div>

                <!-- Burger Button for Mobile -->
                <button @click="toggleMenu" class="burger-btn">
                    <div class="burger-lines">
                        <span :class="['burger-line', isOpen ? 'open' : '']"></span>
                        <span :class="['burger-line', isOpen ? 'open' : '']"></span>
                        <span :class="['burger-line', isOpen ? 'open' : '']"></span>
                    </div>
                </button>
            </div>

            <!-- Mobile Menu -->
            <div :class="['mobile-menu', isOpen ? 'open' : 'closed']">
                <div class="mobile-links">
                    <a href="#Home" @click="closeMenu">الرئيسية</a>
                    <a href="#AboutUs" @click="closeMenu">تعرف علينا</a>
                    <a href="#Dashboard" @click="closeMenu">لوحة البيانات</a>
                    <a href="#SignOut" @click="closeMenu">تسجيل خروج</a>
                    <a href="#SignIn" @click="closeMenu">تسجيل دخول</a>
                    <a href="#SignUp" @click="closeMenu">سجل معنا</a>
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
        },
        closeMenu() {
            this.isOpen = false
        }
    }
}
</script>

<style scoped>
* {
    margin: 0;
    padding: 0;
    font-family: "Cairo", sans-serif;
}
.header {
    background-color: #1f2937;
    color: white;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
}

.nav-container {
    display: flex;
    justify-content: center;
    flex-direction: row-reverse;
    align-items: center;
    padding: 1rem 0;
}

.brand {
    font-size: 1.25rem;
    font-weight: bold;
    color: orange;
}

.desktop-menu {
    display: none;
}

.mainLinks, .access {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
}

.mainLinks {
    margin-right: 2rem;
}

.mainLinks li, .access li {
    margin: 0 1rem;
}

.mainLinks a, .access a {
    color: white;
    text-decoration: none;
    transition: color 0.3s ease;
}

.mainLinks a:hover, .access a:hover {
    color: #4ade80;
}

.burger-btn {
    display: block;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
}

.burger-lines {
    width: 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
}

.burger-line {
    height: 0.125rem;
    background-color: white;
    transition: all 0.3s ease;
    transform-origin: center;
}

.burger-line.open:nth-child(1) {
    transform: rotate(45deg) translateY(0.375rem);
}

.burger-line.open:nth-child(2) {
    opacity: 0;
}

.burger-line.open:nth-child(3) {
    transform: rotate(-45deg) translateY(-0.375rem);
}

.mobile-menu {
    text-align: right;
    overflow: hidden;
    transition: max-height 0.3s ease;
}

.mobile-menu.closed {
    max-height: 0;
}

.mobile-menu.open {
    max-height: 24rem;
    padding-bottom: 1rem;
}

.mobile-links {
    display: flex;
    flex-direction: column;
}

.mobile-links a {
    color: white;
    text-decoration: none;
    padding: 0.5rem 0;
    border-bottom: 1px solid #374151;
    transition: color 0.3s ease;
}

.mobile-links a:hover {
    color: #4ade80;
}

.mobile-links a:last-child {
    border-bottom: none;
}

@media (min-width: 768px) {
    .desktop-menu {
        display: flex;
    }
    
    .burger-btn {
        display: none;
    }
    
    .mobile-menu {
        display: none;
    }
}
</style>