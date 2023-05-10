<template>
    <div class="page-title flex items-center">
        <div class="page-title__rectangle"></div>
        {{ title }}
    </div>
</template>
<script>
export default {
    props: {
        title: {
            type: String
        }
    }
}
</script>
<style lang="scss" scoped>
.page-title {
    color: #F59E0B;
    gap: 8px;
    &__rectangle {
        width: 32px;
        height: 1px;
        background: #F59E0B;
    }
}
</style>