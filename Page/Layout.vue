<template>
    <div>
        <div class="skip">
            <a href="" class="skip__link">본문 바로가기</a>
            <a href="" class="skip__link">주메뉴 바로가기</a>
        </div>
        <TemplatePageHeader />
        <Nav/>
        <TemplatePageContainer :title="title">
            <template v-slot:content>
                <slot></slot>
            </template>
        </TemplatePageContainer>
    </div>
</template>
<script>
export default {
    props: {
        title: {
            type: String,
            default: '',
        },
    },
    head() {
        return {
            title: 'N2M-LOG-MANAGER',
            titleTemplate: '%s - Nuxt',
            meta: [
                { charset: 'utf-8' },
                { name: 'viewport', content: 'width=device-width, initial-scale=1' },
            ],
            link: [
                // { rel: "icon", type: "image/x-icon", href: "/favicon.ico" },
                { rel: "stylesheet", href: "/css/reset.css" },
                { rel: "stylesheet", href: "/css/style.css" },
                { rel: "stylesheet", href: "/css/jquery-ui.css" },
                { rel: "stylesheet", href: "/library/alertifyjs/css/alertify.min.css" },
            ],
            script: [
                { src: "/js/jquery-3.4.1.min.js" },
                { src: "/js/jquery-ui.min.js" },
                { src: "/js/jquery-ui-timepicker-addon.js" },
                { src: "/js/ui.js" },
                { src: "/js/eai-ui.js" },
                { src: "/js/common.js" },
                { src: "/js/init.js" },
                { src: "/library/alertifyjs/alertify.min.js" },
            ]
        }
    },
}
</script>