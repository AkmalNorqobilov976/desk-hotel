<template>
    <div class="text-field flex items-center">
        <span class="text-field__prepend">
            <slot name="prepend">
                <LocationIcon/>
            </slot>
        </span>
        <input 
            class="text-field__input flex-1" 
            v-bind="$attrs"
            :value="value"
            @input="$emit('input', $event.target.value)"
            type="text"
        />
        <slot name="append">
            <Btn class="items-center" :label="'Search'">
                <template #icon>
                    <ArrowRightIcon/>
                </template>
            </Btn>
        </slot>
    </div>
</template>
<script>
import Btn from './Btn.vue'
export default {
  
  components: { Btn },
  props: {
    value: {

    }
  }
}
</script>
<style lang="scss" scoped>
.text-field {
    justify-content: center;
    padding: 4px 4px 4px 24px;
    gap: 16px;
    border: 1px solid #E0E3EB;
    border-radius: 32px;
    &__input {
        flex: 1 1 auto;
        border: none;
        outline: none;
        height: 100%;
    }
}
</style>