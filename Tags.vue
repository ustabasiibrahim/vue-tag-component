<template>
    <div class="tag-container">
        <Tag v-for="(tag, index) in tags" :tag="tag" :index="index" @removeOneTagEvent="removeOneTag($event)" :tagColor="color"/>
        <input type="text"
               placeholder="Enter a tag"
               @keydown.enter="addTag"
               @keydown.backspace="removeTag"
        >
        <div class="error" v-if="error">Bu etiket daha önceden eklenmiş</div>
    </div>
</template>

<script>
    import Tag from '@/components/Tag';

    export default {
        name: "Tags",
        components: {Tag},
        data() {
            return {
                tags: [],
                error: false,
            }
        },
        methods: {
            addTag(e) {
                let text = e.target;
                // eslint-disable-next-line no-unused-vars
                let matchedTag = false;
                if (text.value.length > 0) {
                    this.tags.forEach(tag => {
                        if (tag.toLowerCase() === text.value.toLowerCase()) {
                            matchedTag = true;
                        }
                    });
                    if (!matchedTag) {
                        this.tags.push(text.value);
                        text.value = '';
                    } else {
                        this.error = true;
                        setTimeout(() => {
                            this.error = false;
                        }, 2000);
                    }
                }
            },
            removeTag(e) {
                if (e.target.value <= 0)
                    this.tags.splice(this.tags.length - 1, 1);
            },
            removeOneTag(index) {
                this.tags.splice(index, 1);
            }
        },
        props: {
            value: {
                required: false,
            },
            color: {
                type: String,
                required: false,
                default: "success",
            }
        },
        created() {
            if(this.value) {
                if(this.value.length > 0) {
                    this.tags = this.value.split(',');
                }
            }
        },
        watch: {
            tags() {
                this.$emit("input", this.tags.join(","));
            }
        },
    }
</script>

<style scoped>
    .tag-container {
        border: 1px solid #ccc;
        padding: 20px;
    }

    input {
        outline: none;
        height: 30px;
    }

    .error {
        font-size: 12px;
        color: red;
        margin-top: 15px;
    }
</style>
