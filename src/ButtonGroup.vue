<template>
    <div class="g-button-group">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "ButtonGroup",
        mounted() {
            // console.log(this.$el.children)
            for (let node of this.$el.children) {
                let name = node.nodeName.toLowerCase()
                if(name !== 'button'){
                    console.warn(`g-button-group 组件的子节点应为 g-button, 而你的子节点为${name}`)
                }
            }
        }
    }
</script>

<style scoped lang="scss">
    .g-button-group {
        display: inline-flex;
        vertical-align: middle;

        > .g-button {
            border-radius: 0;

            &:not(:first-child) {
                margin-left: -1px;
            }

            &:first-child {
                border-top-left-radius: var(--border-radius);
                border-bottom-left-radius: var(--border-radius);
            }

            &:last-child {
                border-top-right-radius: var(--border-radius);
                border-bottom-right-radius: var(--border-radius);
            }

            &:hover {
                position: relative;
                z-index: 1;
            }
        }
    }
</style>