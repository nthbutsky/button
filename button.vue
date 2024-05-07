<template>
  <button
    class="relative inline-flex group focus:outline-color-1 rounded-[200px] focus:outline-offset-1"
    :class="{
      'w-full': fullWidth,
    }"
    :type="isForm"
    :disabled="disabled"
    :form="formId"
    v-bind="$attrs"
    @click="onClick"
  >
    <div
      :class="{
        'absolute -z-1 w-full h-full group-hover:blur-[12.5px] group-hover:rounded-[300px] transition ease-in-out':
          !disabled,
        'group-hover:bg-gradient-1': color === 'BLUE' && !disabled,
        'group-hover:bg-gradient-2': color === 'VIOLET' && !disabled,
        'group-hover:bg-gradient-3': color === 'ORANGE' && !disabled,
      }"
    />
    <div
      class="relative z-1 px-4 py-3 min-h-[48px] rounded-[200px] justify-start items-center gap-2 inline-flex shadow-large"
      :class="{
        'w-full justify-center': fullWidth,
        'bg-neutral-100': !filled || !disabled,
        'bg-gradient-1': filled && color === 'BLUE' && !disabled,
        'bg-gradient-2': filled && color === 'VIOLET' && !disabled,
        'bg-gradient-3': filled && color === 'ORANGE' && !disabled,
        'bg-neutral-900-12 cursor-not-allowed': filled && disabled,
        'cursor-not-allowed': !filled && disabled,
      }"
    >
      <component
        :is="icon"
        v-if="icon"
        class="w-6 h-6"
        :class="{
          'text-color-1': !filled && color === 'BLUE',
          'text-color-3': !filled && color === 'VIOLET',
          'text-color-5': !filled && color === 'ORANGE',
          'text-neutral-100': filled,
          'text-neutral-400': disabled && !filled,
        }"
      />
      <span
        class="font-5 flex items-center"
        :class="{
          'text-neutral-400': !filled,
          'text-neutral-100': filled,
          'text-transparent bg-clip-text bg-gradient-1': !filled && color === 'BLUE' && !disabled,
          'text-transparent bg-clip-text bg-gradient-2': !filled && color === 'VIOLET' && !disabled,
          'text-transparent bg-clip-text bg-gradient-3-font':
            !filled && color === 'ORANGE' && !disabled,
        }"
      >
        {{ text }}
      </span>
    </div>
  </button>
</template>

<script lang="ts" setup>
import {
  FunctionalComponent, SVGAttributes, computed,
} from 'vue';

import {
  TColorScheme, COLOR_SCHEME,
} from '@/types/color-scheme';

interface IProps {
  color?: TColorScheme;
  text?: string;
  icon?: FunctionalComponent<SVGAttributes>;
  disabled?: boolean;
  fullWidth?: boolean;
  formId?: string;
  filled?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  color: COLOR_SCHEME.BLUE,
  text: '',
  icon: undefined,
  disabled: false,
  fullWidth: false,
  formId: undefined,
  filled: false,
});

const isForm = computed(() => {
  return props.formId ? 'submit' : 'button';
});

// eslint-disable-next-line func-call-spacing, no-spaced-func
const emits = defineEmits<{
  (e: 'click'): void;
}>();

function onClick() {
  emits('click');
}
</script>
