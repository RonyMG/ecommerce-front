<template>
    <div v-for="(menuItem, index) in menuItems" :key="index">
        <a :href="`#${formatToKebabCase(menuItem)}`">
            {{ menuItem }}
        </a>
    </div>

    <div class="navbar__nav-select">
        <div class="dropdown">
            <button class="button-navbar dropdown-toggle flex-nowrap d-flex align-items-center p-0" type="button" data-bs-toggle="dropdown"
                    aria-expanded="false">
                Language
                <svg width="20" height="20" viewBox="0 0 20 20" class="nav-select__icon-world"
                    xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M10 0C4.476 0 0 4.476 0 10s4.476 10 10 10 10-4.476 10-10S15.524 0 10 0zm7.79 6.129h-3.326c-.363-1.79-.972-3.314-1.742-4.4a8.748 8.748 0 0 1 5.068 4.4zM13.548 10c0 .923-.064 1.782-.173 2.58h-6.75A19.058 19.058 0 0 1 6.452 10c0-.923.064-1.782.173-2.58h6.75c.109.798.173 1.657.173 2.58zM10 1.29c1.085 0 2.476 1.779 3.15 4.839h-6.3C7.525 3.069 8.916 1.29 10 1.29zm-2.722.44C6.512 2.81 5.9 4.335 5.536 6.129H2.21a8.748 8.748 0 0 1 5.068-4.4zM1.29 10c0-.9.137-1.766.391-2.58h3.65a19.723 19.723 0 0 0 0 5.161H1.68A8.655 8.655 0 0 1 1.291 10zm.92 3.871h3.326c.363 1.79.972 3.314 1.742 4.4a8.748 8.748 0 0 1-5.068-4.4zM10 18.71c-1.085 0-2.476-1.779-3.15-4.839h6.3c-.674 3.06-2.065 4.839-3.15 4.839zm2.722-.44c.766-1.08 1.379-2.605 1.742-4.399h3.326a8.748 8.748 0 0 1-5.068 4.4zm1.947-5.69a19.723 19.723 0 0 0 0-5.161h3.65c.254.815.39 1.682.39 2.581 0 .9-.136 1.766-.39 2.58h-3.65z"
                    fill="#FFF" fill-rule="nonzero" />
                </svg>
                <!-- Español<%# <%= (:language_title) %> -->
            </button>

            <ul class="dropdown-menu px-2">
                <!-- <%# <% (I18n.available_locales - [@locale.to_sym]).each do |lang| %> -->
                <li>
                    English
                    <!-- <%# <%= link_to t('language_title', locale: lang.to_s), 
                                "/#{lang.to_s}/" + (t("routes.#{controller_name}.#{action_name}", locale: lang.to_s) || '').gsub(':slug', (params[:slug] || '')),
                                class: 'dropdown-item'%> -->
                </li>
                <!-- <%# <% end %>  -->
                <li>
                    Español
                    <!-- <%# <%= link_to t('language_title', locale: lang.to_s), 
                                "/#{lang.to_s}/" + (t("routes.#{controller_name}.#{action_name}", locale: lang.to_s) || '').gsub(':slug', (params[:slug] || '')),
                                class: 'dropdown-item'%> -->
                </li>
            </ul>

        </div>
    </div>
</template>

<script>
export default {
    props: ["menuItems"],
    methods: {
        formatToKebabCase(text) {
            return text
            .toLowerCase() // Convertir a minúsculas
            .replace(/\s+/g, '-') // Reemplazar espacios con guiones
            .replace(/[^\w-]+/g, ''); // Eliminar caracteres no alfanuméricos
        }
    }
}
</script>

<style>

</style>