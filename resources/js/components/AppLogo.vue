<script setup lang="ts">
import type { HTMLAttributes } from 'vue';

defineOptions({
    inheritAttrs: false,
});

interface Props {
    className?: HTMLAttributes['class'];
}

defineProps<Props>();
</script>

<template>
    <img
        src="https://assets-cdn.signable.co.uk/images/signable.blue.png"
        alt="Signable"
        :class="className"
        v-bind="$attrs" />
</template>
