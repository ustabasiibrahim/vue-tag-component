<template>
    <span class="tag" :class="selectedTheme">
            <span class="content">{{ tag }}</span>
            <span class="close" @click="$emit('removeOneTagEvent', index)">x</span>
        </span>
</template>

<script>
    export default {
        name: "Tag",
        props: [ "tag", "index", "tagColor"],
        data() {
            return {
                selectedTheme: null,
            }
        },
        created() {
            this.selectedTheme = this.tagColor;
        }
    }
</script>

<style scoped>

    .primary {
        background-color: #c2a497;
    }
    .info {
        background-color: #5e5e75;
    }
    .warning {
        background-color: #ed9c2d;
    }
    .success {
        background-color: #6fac65;
    }
    .danger {
        background-color: #f44336;
    }
    .tag {
        padding: 10px;
        cursor: default;
        font-size: 14px;
        margin-right: 10px;
        color: #FFF;
    }

    .tag .close {
        font-size: 12px;
        cursor: pointer;
        margin-left: 10px;
        font-weight: bold;
    }


</style>
