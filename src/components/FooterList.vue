<template>
    <div class="footer-list">
        <h3 class="footer-list__title">{{ title }}</h3>
        <ul class="flex">
            <li v-for="list, i in lists" :key="i">
                {{ list }}
            </li>
        </ul>
    </div>
    
</template>

<script>
export default {
    props: {
        title: {
            type: String
        },
        lists: {
            type: Array
        }
    }
}
</script>

<style lang="scss" scoped>
.footer-list {
    &__title {
        font-weight: 600;
        font-size: 18px;
        line-height: 22px;
        text-transform: capitalize;
        color: #0E1735;
    }

    ul {
        margin-top: 24px;
        list-style: none;
        flex-direction: column;
        gap: 18px;
        li {
            font-weight: 400;
            font-size: 14px;
            line-height: 18px;
            text-transform: capitalize;
            color: #888B97;
        }
    }
}
</style>