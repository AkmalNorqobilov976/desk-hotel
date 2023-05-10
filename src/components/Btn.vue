<template>
  <div class="btn flex items-center" :class="[className && className]">
    <slot>{{ label }}</slot>
    <span class="btn__icon">
      <slot name="icon">
        <i :class="icon"></i>
      </slot>
    </span>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
    },
    bgColor: {
      type: String,
    },
    color: {
      type: String,
    },
    icon: {
      type: String,
    },
    className: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  &__icon {
    display: inline;
  }
}
</style>