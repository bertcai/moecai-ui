<template>
    <svg class="icon" aria-hidden="true">
        <use :xlink:href="`#i-${name}`"></use>
    </svg>
</template>

<script>
    export default {
        name: "g-icon",
        props: ["name"]
    }
</script>

<style scoped lang="scss">
    .icon {
        height: 1em;
        width: 1em;
    }
</style>