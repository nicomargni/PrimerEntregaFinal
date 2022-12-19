<template>
    <div>
        <!-- Slot sin nombre -->
        <slot></slot>
        <!-- Slot con nombre -->
        <slot name="precio">$</slot>
    </div>
</template>

<script>
export default {
    name: 'SlotPrueba',

};
</script>

<style scoped>

</style>