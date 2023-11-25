<template>
    <footer id="Footer" class="footer">
        <div class="main-container footer__content">
            <span>Sitemap</span>

            <div class="footer__row footer__row--sitemap">
                <template v-for="(menuItem, index) in menuItems" :key="index">
                    <a :href="`#${formatToKebabCase(menuItem)}`" class="footer__sitemap-item">
                        {{ menuItem }}
                    </a>
                </template>
            </div>

            <span>Contact</span>
            <div class="footer__row">
                800 3234 3432
            </div>
            <span>Follow us</span>
            <div class="footer__row">
                <img src="" class="footer__icon" alt=""> <img src="" class="footer__icon" alt="">
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'FooterC',

    inject: ["menuItems"],
    
    mounted() {
        this.updateFooterHeight();

        window.addEventListener('resize', this.updateFooterHeight);
    },

    beforeDestroy() {
        window.removeEventListener('resize', this.updateFooterHeight);
    },

    methods: {

        updateFooterHeight() {
            const footer = document.getElementById('Footer');
            if (footer) {
                const footerHeight = footer.getBoundingClientRect().height;
                document.documentElement.style.setProperty('--footer-height', `${footerHeight}px`);
            }
        },

        formatToKebabCase(text) {
            return text
            .toLowerCase() // Convertir a minúsculas
            .replace(/\s+/g, '-') // Reemplazar espacios con guiones
            .replace(/[^\w-]+/g, ''); // Eliminar caracteres no alfanuméricos
        }
    },

}
</script>

<style>

</style>