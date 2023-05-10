<template>
    <div class="recommendation-card">
        <button v-if="btnLabel" class="inline-flex items-center">
            <component :is="icon" :color="btnColor" height="13"/>
            {{ btnLabel }}
        </button>
        <div class="recommendation-card__img">
            <slot name="image">
                <img :src="image" alt="">
            </slot>
        </div>
        <div class="recommendation-card__body">
            <h3 class="recommendation-card__body--title">
                {{ title }}
            </h3>
            <p class="recommendation-card__body--description">
                {{ description }}
            </p>
        </div>
        <div class="recommendation-card__user flex items-center">
            <div v-if="userImage" class="recommendation-card__user--image">
                <slot name="userImage">
                    <img :src="userImage" alt="">
                </slot>
            </div>
            <div class="recommendation-card__user--info">
                <h3>{{ userName }}</h3>
                <p>{{ address }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        image: { },
        title: {
            type: String
        },
        description: {
            type: String
        },
        userImage: {

        },
        userName: {
            type: String
        },
        address: {
            type: String
        },
        btnColor: {
            type: String,
            default: '#1D4ED8'
        },
        btnBgColor: {
            type: String,
            default: '#DBEAFE'
        },
        btnLabel: {
            type: String
        },
        icon: {}
    }
}
</script>

<style lang="scss" scoped>
.recommendation-card {
    width: 340px;
    min-width: max-content;
    position: relative;
    button {
        border: none;
        outline: none;
        min-width: max-content;
        color: v-bind(btnColor);
        background: v-bind(btnBgColor);
        padding: 9px 18px;
        border-radius: 32px;
        gap: 12px;
        position: absolute;
        left: 16px;
        top: 332px;
    }
    &__img {
        width: 100%;
        height: 382px;
        overflow: hidden;
        img {
            object-fit: cover;
        }
    }
    &__body {
        margin: 24px 0;
        &--title {
            font-weight: 500;
            font-size: 24px;
            line-height: 32px;
            color: #0E1735;
            margin-bottom: 8px;
        }
        &--description {
            font-weight: 500;
            font-size: 20px;
            line-height: 32px;
            color: #3C4563;
        }
    }

    &__user {
        gap: 16px;
        &--image {
            width: 40px;
            height: 40px;
            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        }

        &--info {
            h3 {
                font-weight: 500;
                font-size: 18px;
                line-height: 24px;
                color: #0E1735;
            }

            p {
                font-weight: 500;
                font-size: 14px;
                line-height: 22px;
                color: #888B97;
            }
        }
    }
}
</style>