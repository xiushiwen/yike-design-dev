<template>
  <button
    :class="[
      bem([type, status, shape, size], {
        loading: loading,
        long: long,
        disabled: disabled,
      }),
    ]"
    :disabled="disabled || loading"
  >
    <svg v-if="loading" viewBox="25 25 50 50">
      <circle r="20" cy="50" cx="50"></circle>
    </svg>

    <slot v-else name="icon" />
    <slot></slot>
  </button>
</template>

<script lang="ts">
export default {
  name: 'YKButton',
}
</script>
<script setup lang="ts">
import { ButtonProps } from './button'

import { createCssScope } from '../../utils/bem'

const bem = createCssScope('button')

defineOptions({
  name: 'YKButton',
})
withDefaults(defineProps<ButtonProps>(), {
  type: 'primary',
  size: 'l',
  shape: 'default',
  long: false,
  loading: false,
  disabled: false,
})
</script>
