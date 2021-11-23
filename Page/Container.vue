<template>
    <div class="container">
        <div class="content-wrap">
            <section class="section-wrap">
                <div class="title-txt">
                    <h3 class="title-txt__medium">{{title}}</h3>
                </div>
                <slot name="content"/>
            </section>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        title: {
            type: String,
            default: ''
        }
    }
}
</script>