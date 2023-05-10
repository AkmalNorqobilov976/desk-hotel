<template>
    <div class="header-card">
        <div class="header-card__images">
            <slot name="avatar">
                <div class="header-card__images--img">
                    <img :src="img" alt=""/>
                </div>
            </slot>
        </div>
        <div class="header-card__info">
            <h3 class="header-card__info--title">
                {{ title }}
            </h3>
            <p class="header-card__info--description">
                {{ description }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        img: {
            type: String
        },
        title: {
            type: String
        },
        description: {
            type: String
        }
    }
}
</script>

<style lang="scss" scoped>
.header-card {
    display: inline-flex;
    align-items: center;
    background: white;
    padding: 29px 24px;
    box-shadow: 0px 11px 48px rgba(51, 51, 51, 0.06);
    border-radius: 32px;
    gap: 16px;
    &__images{
        position: relative;
    }

    &__info {
        h3 {
            min-width: max-content;
            font-weight: 600;
            font-size: 16px;
            line-height: 24px;
            color: $indigo;
        }
        p {
            width: max-content;
            margin-top: 2px;
            font-weight: 400;
            font-size: 12px;
            line-height: 20px;
            color: #68799F;
        }
    }
}
</style>