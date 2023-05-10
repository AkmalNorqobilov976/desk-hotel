<template>
    <div class="benifit-card flex">
        <div class="benifit-card__icon flex items-center justify-center">
            <component :is="icon"/>
        </div>
        <div class="benifit-card__lists">
            <div class="benifit-card__lists--item">
                <h3>{{ title }}</h3>
                <p>{{ description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        icon: {
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
.benifit-card {
    gap: 30px;
    &__icon {
        align-self: flex-start;
        border-radius: 50%;
        padding: 16px;
        background: #1EA59A10;    }

    &__lists {
        &--item {
            h3 {
                font-weight: 700;
                font-size: 24px;
                line-height: 25px;
                letter-spacing: 0.352941px;
                color: #000B70;
            }

            p {
                font-family: 'Lexend';
                font-weight: 400;
                font-size: 18px;
                line-height: 28px;
                color: #B1B6CA;
            }

        }
    }
}
</style>