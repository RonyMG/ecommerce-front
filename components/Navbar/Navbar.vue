<template>
    <header class="header__container">

        <nav id="Header" class="header__nav navbar navbar-expand-lg">
            <div class="main-container container-fluid h-auto">
            <a class="navbar-brand" href="#">logotipo</a>
            <div class="d-flex">
                <button class="button-menu d-flex d-xl-none"
                type="button" 
                data-bs-toggle="offcanvas" 
                data-bs-target="#offcanvasExample"
                aria-controls="offcanvasExample">
                <span>l</span><span>l</span><span>l</span>
                </button>
                <div class="collapse navbar-collapse justify-content-end" id="navbarTogglerDemo02">
                <div class="header__menu">
                    <NavMenu></NavMenu>
                </div>
                </div>
            </div>
            </div>
        </nav>

        <div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">

            <!--
            <div class="offcanvas-header">

            --Sidebar Title
            <h5 class="offcanvas-title" id="offcanvasExampleLabel"></h5>

            --Sidebar Close button
            <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>

            </div>
            -->

            <div class="offcanvas-body main-container pe-0 me-0">
                <div class="header__menu header__menu--mobile">
                    <NavMenu></NavMenu>
                </div>
            </div>
        </div>
        
        </header>

</template>

<script>

import NavMenu from './NavMenu.vue'

export default {
    components: { NavMenu },

    name: 'NavbarC',
    
    mounted() {
        this.updateHeaderHeight();

        window.addEventListener('resize', this.updateHeaderHeight);
    },

    beforeDestroy() {
        window.removeEventListener('resize', this.updateHeaderHeight);
    },

    methods: {

        updateHeaderHeight() {
            const header = document.getElementById('Header');
            if (header) {
                const headerHeight = header.getBoundingClientRect().height;
                document.documentElement.style.setProperty('--header-height', `${headerHeight}px`);
            }
        },

    }
}
</script>

<style>

</style>