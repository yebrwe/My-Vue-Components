<template>
    <transition name="fade">
        <div class="dim-layer dim-pop" v-show="show">
            <div class="dimBg"></div>
            <div class="pop-layer">
                <div class="pop-container">
                    <div class="modal__header">
                        <h3 class="hidden">{{title}}</h3>
                    </div>
                    <div class="modal__body">
                        <section class="modal__service-request">
                            <h4 class="modal__heading1">{{title}}</h4>
                            <div class="content-wrap scroll-inner">
                                <section class="section-wrap">
                                    <slot></slot>
                                </section>
                            </div>
                            <div class="data-unit__buttons">
                                <a class="data-unit__button data-unit__button-apply" @click="apply">적용</a>
                                <a class="data-unit__button" @click="close">닫기</a>
                                <a class="btn-layerClose data-unit__button" @click="close">모달 닫기</a>
                            </div>
                        </section>
                    </div>
                </div>
            </div>
        </div>
    </transition>
</template>
<script>
export default {
    props: {
        show: {
            type: Boolean,
            default: false
        },
        title: {
            type: String,
            default: ''
        }
    },
    methods: {
        apply() {
            this.$emit('apply');
        },
        close() {
            this.$emit('close');
        }
    }
}
</script>
<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>