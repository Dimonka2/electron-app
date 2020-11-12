<template>
    <div v-show="isActive"
        :aria-hidden="! isActive"
        role="tabpanel"
        :id="computedId"
    >
        <slot />
    </div>
</template>
<script>
    export default {
        props: {
            name: {
                type: String,
                required: true
            },
            selected: { default: false},
            badge: String
        },
        data() {
            return {
                isActive: false
            };
        },
        computed: {
            computedId() {
                return this.id ? this.id : this.name.toLowerCase().replace(/ /g, '-')
            },
            hash() {
                if (this.isDisabled) {
                    return '#'
                }
                return '#' + this.computedId
            }
        },

        mounted() {
            this.isActive = this.selected;
        }
    }
</script>