<template>
    <div class="g-button-group">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "button-group",
        mounted() {
            for(let node of this.$el.children) {
                let name = node.nodeName.toLowerCase()
                if (name !== 'button') {
                    console.warn(`g-button-group 的子元素应该全是 g-button，但是你写的是 ${name}`)
                }
            }
        }
    }
</script>

<style scoped>
    .g-button-group {
        display: flex;
        vertical-align: middle;
    }
</style>